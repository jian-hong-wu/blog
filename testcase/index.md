[上一頁](https://jian-hong-wu.github.io/blog/)

**This operation guide only applies to jlo-server01!**

## <font color="#0091FF">為 Sonic 測試設置環境:</font>

在 Sonic 測試開始前，下列項目應於伺服器端設置完成：

1.  支援 Python 2.7 (Ansible 現在只支援 Python 2.7 )

2.  Current test source code is based on sonic 202012_latest branch, test server is jlo-server01, server OS is Ubuntu 20.04.   
    2.1 Our default git source directory is under ~/sonic/src/202012_latest directory. So the full path will be 
        jlo@jlo-server01:/home/jlo/sonic/src/202012_latest.    
    2.2 可使用下列指令下載 sonic-mgmt source code from git, you can also get the sonic build image from git.         
    &nbsp;&nbsp;&nbsp;&nbsp;$ git clone https://github.com/Azure/sonic-mgmt   
    &nbsp; &nbsp; &nbsp; &nbsp; $ git clone https://github.com/Azure/sonic-buildimage   
    2.3 Follow sonic build instructions to build sonic-mgmt-dev container and docker-ptf container.   
    2.4 <font color="#0091FF"> ~$: points to prject root directory: /home/jlo/sonic/src/202012_latest. </font>   
    
3.  ~$/sonic-mgmt/ansible/veos-vm/images 這裡save有VM檔案   
    For now, we copy these two files under ~/veos-vm/images directory    
    這裡有兩個檔案:   
    &nbsp;&nbsp;&nbsp;&nbsp;a.&nbsp;&nbsp;5242880 Aboot-veos-serial-8.0.0.iso and   
    &nbsp;&nbsp;&nbsp;&nbsp;b. 336789504 vEOS-lab-4.20.15M.vmdk  
    [可點選從此處下載](https://www.arista.com/en/support/software-download)   

4.  檢查 `sonic-mgmt-dev` and `docker-ptf`是否被下載到 docker 裡面了，可以使用指令 docker images 確認     
![image001](https://jian-hong-wu.github.io/blog/testcase/image001.png)  
    (Please refer to Sonic document to learn how to build these two containers.)   

5.  在 server 的環境, 建立一個名為 sonic-mgmt-work 的 container  
    $ cd ~$   
    ~$ docker run --name sonic-mgmt-work -it sonic-mgmt-dev:ec202012 /bin/bash  
    
    *NOTE : 從這裡開始所有步驟都在 container `sonic-mgmt-dev` 中執行*

    5.1 You have names a container called "sonic-mgmt-work". after you exit the container (type ctrl-D, or exit()), docker ps -a -f "name=sonic-mgmt-work" will list the container.   
    5.2 Docker ps will not show a stopped process.   
    5.3 To continue your work, try $ docker exec -it sonic-mgmt-work /bin/bash    
    5.4 Please refer to the docker manual for how to commit the changes and create a newer imager.    
         
6.  Prepare Testbed Configuration  (若使用 $ ./server.sh ，則這部份可以跳過)  
    進入 docker container 後，要修改 testbed configuration files 以反映 lab setup。  

    Update the server management IP in [`ansible/veos`](/ansible/veos).  
    Update the testbed server credentials in [`ansible/group_vars/vm_host/creds.yml`](/ansible/group_vars/vm_host/creds.yml).  
    Update the server network configuration for the VM and PTF management interfaces in [`ansible/host_vars/STR-ACS-SERV-01.yml`](/ansible/host_vars/STR-ACS-SERV-01.yml).  
    ```
      -  external_port: server trunk port name (connected to the fanout switch)  
      -  mgmt_gw: ip of the gateway for the VM management interfaces  
      -  mgmt_prefixlen: prefixlen for the management interfaces
    ```
    以下列指令檢查 ansible 是否可以訪問此主機  
    ansible -m ping -i veos vm_host_1

    Update /ansible/group_vars/vm_host/main.yml with the location of the veos files or veos file name if you downloaded a diferent version  
    Update the VM IP addresses in the [`ansible/veos`](/ansible/veos) inventory file. These IP addresses should be in the management subnet defined above.  
    Update the VM credentials in `ansible/group_vars/eos/creds.yml`.
    ```
    cat <<EOT >> /data/sonic-mgmt/ansible/group_vars/eos/creds.yml
    ---
    ansible_password: '123456'
    ansible_user: admin
    EOT
    ```
    Update the docker registry information in [`vars/docker_registry.yml`](/ansible/vars/docker_registry.yml).

7.  Setup VMs on the Server (若VMs已經存在請跳過此步驟)

    a. 啟動 virtual machine
    ```
    # /data/sonic-mgmt/ansible
    ./testbed-cli.sh start-vms server_1 password.txt
    ```
    請注意： password.txt 是 ansible Vault 密碼文件名/路徑。 Ansible 允許用戶使用 ansible-vault 來加密密碼文件。默認情況下，此 shell 腳本需要密碼文件。如果您不使用 ansible-vault ，只需創建一個空文件並將文件名傳遞給命令行。 文件名和位置由用戶創建和維護。
    ```
    echo "" > ./password.txt
    ```

    b. 檢查所有 VM 是否已啟動並正在運行
    ```
    $ ping "vm_ip"
    ```
    c. 一般情況下不關閉VMs，若有需要可使用  
    $ cd sonic-mgmt/ansible/  
    $ ./testbed-cli.sh stop-vms server_1 ~/.password
    
8.  更新 testbed.csv。至少應該更新 PTF 管理界面設置。

## Topology 與對應的 IP address

1. In server
- Br107 <-> enx000ec6a96640 (192.168.40.25)
- Br1 <-> enx00e04c680215 (10.250.2.44)
- NIC#3 <-> ens2f0np0
 
2. VMs  
VM0200 : 10.250.2.100  
….  
VM0267 : 10.250.2.163

3. In Root Fanout  
10.250.1.2
 
4. In Leaf Fanout  
10.250.1.3
 
5. In DUT  
10.250.1.4

## <font color="#0091FF">Sonic 測試的主要步驟:</font>

#### 1.  Sonic 測試主要在 docker-sonic-mgmt container內進行，首先你要進入 docker-sonic-container內，switch to ansible directory. Once you are in ansible directory, look for testbed.csv file. Testbed.csv file lists all the test cases for test.

Once you are in the directory.  
    a. Deploy topology  
    b. Deploy minigraph  
    c. Run test  
    d. Collect test results.

#### 2.  下面是會用到的command:

//查看存在的 images  
$ docker image ls

![image](https://jian-hong-wu.github.io/blog/testcase/image.png)

//在 server 的環境, 建立一個名為 sonic-mgmt-name 的 container  
$ docker run -it --name sonic-mgmt-name sonic-mgmt-dev:ec202012 /bin/bash  
//或者進入一個已經存在的 container 並跳到[步驟a](https://jian-hong-wu.github.io/blog/testcase/#a-deploy-topology)  
$ docker exec -it sonic-mgmt-name /bin/bash

//在 container 裡進入資料夾 sonic-mgmt  
$ cd sonic-mgmt/

//進入資料夾 server_config (在taipei lab跳過這步驟)  
$ cd server_config

//選擇server n=1~6 (在taipei lab跳過這步驟)  
$ ./server.sh n

//返回上一層並進入資料夾 ansible  
$ cd ../ansible/

$ vi host_vars/STR-ACS-SERV-02-1.yml //在tainan lab跳過這步驟  
Confirm this line is correct : external_port: ens2f0np0

check the IP of ens2f0np0 in the **server** //在tainan lab跳過這步驟  
$ ifconfig ens2f0np0 or $ ifconfig ens2f0np0 10.250.2.44

//回到 container，查看檔案 testbed.csv，並決定要測試的 topology，根據要使用的VM進行調整  
$ vi [testbed.csv](https://github.com/jian-hong-wu/blog/blob/gh-pages/testbed.csv/testbed.csv/)

#### a. deploy topology
//新增一個 topology，vmbase 為 VM0232，名稱為 2-4_t0，設定密碼 ~/.password，使用帶有 lastest 標籤的 PTF image 創建 PTF container  
$ ./[testbed-cli.sh](https://github.com/Azure/sonic-mgmt/blob/master/ansible/testbed-cli.sh) -b VM0200 [add-topo](https://jian-hong-wu.github.io/blog/testcase/addtopo/) 2-4_t0 ~/.password -e ptf_imagetag=latest

#### b. deploy minigraph
//設定 inventory = lab， 指定目標為 as7726-32x-1，名稱為 2-4_t0，將新生成的 minigraph 保存並部署到目標 DUT  
$ [ansible-playbook](https://jian-hong-wu.github.io/blog/testcase/playbook/) -i lab [config_sonic_basedon_testbed.yml](https://jian-hong-wu.github.io/blog/testcase/config_sonic_basedon_testbed/) -l as7726-32x-1 -e testbed_name=2-4_t0 -e deploy=true -e save=true

#### c. run test
//testcase 檔案位於 ~/sonic-mgmt/ansible/roles/test/vars/testcases.yml，選擇執行 testcase 中的 syslog  
$ ansible-playbook -i lab --limit as7726-32x-1 [test_sonic.yml](https://jian-hong-wu.github.io/blog/testcase/test_sonic/) -e testbed_name=2-4_t0 -e ptf_host=ptf2-4 -e vm_file=veos -e testcase_name=syslog -vvvv

//返回上一層並進入資料夾 tsets  
$ cd ../tests

//用 py .test 執行測試 test_syslog.py  
$ py.test --inventory=lab --host-pattern=2-4_t0 --module-path ../ansible/library/ --testbed=2-4_t0 --testbed_file=../ansible/testbed.csv ./syslog/test_syslog.py --log-level=DEBUG -vvvv --show-capture=stdout --duration=0

#### d. remove topology
//返回上一層並進入資料夾 ansible  
$ cd ../ansible

//移除 topology 2-4_t0  
$ ./testbed-cli.sh remove-topo 2-4_t0 ~/.password

//離開docker  
$ exit

## <font color="#0091FF">testbed-cli.sh命令詳解:</font>

testbed-cli.sh是用來設定testbed的configuration用的。testbed-cli.sh設定testbed的介面。

#### 1. 用例說明:


用例一:  	
    可用來啟動及停止virtual machine。  
    ./testbed-cli.sh [選項] (start-vms | stop-vms) <server-name> <vault-password-file>
    
用例二:  
    可用來啟動及停止topology。  
    ./testbed-cli.sh [選項] (start-topo-vms | stop-topo-vms) <topo-name> <vault-password-file>
	
用例三:  
    可用來增加及移除topology。  	
    ./testbed-cli.sh [選項] (add-topo | remove-topo | renumber-topo | connect-topo) <topo-name> <vault-password-file>
	
用例四:  
    更新測試topology的狀態。  
    ./testbed-cli.sh [選項] refresh-dut <topo-name> <vault-password-file>
	
用例五:
    連接到虛擬機，中斷到虛擬機的連接。  
    ./testbed-cli.sh [選項] (connect-vms | disconnect-vms) <topo-name> <vault-password-file>
	
用例六:  
    可用來configure topology。  
    ./testbed-cli.sh [選項] config-vm <topo-name> <vm-name> <vault-password-file>
	
用例七:  
    可用來創建及部件message。  
    ./testbed-cli.sh [選項] (gen-mg | deploy-mg | test-mg) <topo-name> <inventory> <vault-password-file>
	
用例八:  
    可用來創建及destroy k8s server。  
    ./testbed-cli.sh [選項] (create-master | destroy-master) <k8s-server-name> <vault-password-file>

#### 2. 選項(Options):  
    -t <tbfile>      : testbed CSV file name (default: 'testbed.csv')  
    -m <vmfile>    : virtual machine file name (default: 'veos')  
    -k <vmtype>    : vm type (veos|ceos) (default: 'veos')  
    -n <vm_num>   : vm num (default: 0)  
    -b <vmbase>    : Specify the VM Base ID the format is VM0100, VM0201   
                    (default: parsing from testbed.csv)  
    -s <msetnumber> : master set identifier on specified <k8s-server-name>   
                    (default: 1)  
    -d <dir>         : sonic vm directory (default: /var/ubuntu/sonic-vm  
	
#### 3. 位置變數(Positional Arguments):

    <server-name>         : Hostname of server on which to start VMs  
    <vault-password-file>    : Path to file containing Ansible Vault password  
    <topo-name>          : Name of the target topology  
    <inventory>           : Name of the Ansible inventory containing the DUT  
    <k8s-server-name>     : Server identifier in form k8s_server_{id}, corresponds  
                          to k8s_ubuntu inventory group name  
    <vmbase>             : 指定虛擬機(VM) base ID and the format is   
   VM01xx or VM02xx   
   (xx = 01~63, default: parsing from testbed.csv)  
<style>  
.tablelines table, .tablelines td, .tablelines th {  
        border: 1px solid black;  
        }  
</style>  

| Cost of VMs | 0台VM | 4台VMs | 6台VMs | 8台VMs | 24台VMs | 32台VMs | 64台VMs |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Topologies | ptf32 | t0 | t0-16 | t0-56 | t1-lag | t1 | t1-64 |
| | ptf64 | t0-64 | | t1-8vm | t1-64-lag | | |
| | | t0-64-32 | | t1-8vm-lag | | | |
| | | t0-52 | | | | | | 
| | | t0-116 | | | | | | 
| | | | | | | | | 
{: .tablelines}


#### 4. 範例說明:

啟動伺服器上所有的虛擬機:  
    ./testbed-cli.sh start-vms 'server-name' ~/.password  
重新啟動伺服器上部份的虛擬機(VMs):  
    ./testbed-cli.sh start-vms server-name vault-password-file -e respin_vms=[vm_list]  
    // vm_list is separated by comma and shouldn't have space in the list.  
    // e.g., respin_vms=[VM0310,VM0330]  
啟動後暫停部份的虛擬機(VMs):  
    ./testbed-cli.sh start-vms server-name vault-password-file -e batch_size=2   
    -e interval=60  
開啟虛擬機(VMs)的自動重啟功能:  
    ./testbed-cli.sh start-vms server-name vault-password-file -e autostart=yes  
啟動VMs for specified topology on server:  
    ./testbed-cli.sh start-topo-vms 'topo-name' ~/.password  
停止all VMs on a server:  
    ./testbed-cli.sh stop-vms 'server-name' ~/.password  
停止VMs for specified topology on server:  
    ./testbed-cli.sh stop-topo-vms 'topo-name' ~/.password  	    
佈建a topology on a server:  
    ./testbed-cli.sh add-topo 'topo-name' ~/.password  
    Optional argument for add-topo:  
      -e ptf_imagetag=<tag> # Use PTF image with specified tag for creating PTF # container  
	    
移除a topology on a server:  
    ./testbed-cli.sh remove-topo 'topo-name' ~/.password  
重新排序a topology on a server:  
    ./testbed-cli.sh renumber-topo 'topo-name' ~/.password  
連接到a topology:  
    ./testbed-cli.sh connect-topo 'topo-name' ~/.password  
刷新DUT in a topology:  
    ./testbed-cli.sh refresh-dut 'topo-name' ~/.password  
配置a VM on a server:  
    ./testbed-cli.sh config-vm 'topo-name' 'vm-name' ~/.password  
創建minigraph for DUT in a topology:  
    ./testbed-cli.sh gen-mg 'topo-name' 'inventory' ~/.password  
佈建minigraph to DUT in a topology:  
    ./testbed-cli.sh deploy-mg 'topo-name' 'inventory' ~/.password  
      gen-mg, deploy-mg, test-mg supports enabling/disabling data ACL   
      with parameter  
        -e enable_data_plane_acl=true  
        -e enable_data_plane_acl=false  
        by default, data acl is enabled  
創建伺服器上的Kubernetes master:  
    ./testbed-cli.sh -m k8s_ubuntu create-master 'k8s-server-name'  ~/.password  
銷毀伺服器上的Kubernetes master:  
    ./testbed-cli.sh -m k8s_ubuntu destroy-master 'k8s-server-name' ~/.password  
你應當在你的testbed CSV file 裏面定義你的topology。  
