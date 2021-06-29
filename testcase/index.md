[上一頁](https://jian-hong-wu.github.io/blog/)

## <font color="#0091FF">Sonic 測試的主要步驟:</font>

#### 1.  Sonic 測試主要在 docker-sonic-mgmt container內進行，首先你要進入 docker-sonic-container內，switch to ansible directory. Once you are in ansible directory, look for testbed.csv file. Testbed.csv file lists all the test cases for test.

Once you are in the directory.

    a. Deploy topology
    b. Deploy minigraph
    c. Run test
    d. Collect test results.

#### 2.  下面是會用到的command:

//查看存在的 images

docker image ls

![image](https://jian-hong-wu.github.io/blog/testcase/image.png)

//使用名為 docker-sonic-mgmt 的 image 創建一個 container 命名為 test，並執行 bash

docker run -it --name test docker-sonic-mgmt bash

//在 container 裡進入資料夾 sonic-mgmt

cd sonic-mgmt/

//進入資料夾 server_config

cd server_config

//執行 server.sh

./server.sh 2

//返回上一層並進入資料夾 ansible

cd ../ansible/

//查看檔案 testbed.csv，並決定要測試的 topology

vi [testbed.csv](https://github.com/jian-hong-wu/blog/blob/gh-pages/testbed.csv/testbed.csv/)

#### a. deploy topology
//新增一個 topology，vmbase 為 VM0200，名稱為 2-7_t0，設定密碼 ~/.password，設定額外參數 ptf_imagetag=lastest 給 ansible-playbook 使用

./[testbed-cli.sh](https://github.com/Azure/sonic-mgmt/blob/master/ansible/testbed-cli.sh) -b VM0200 [add-topo](https://jian-hong-wu.github.io/blog/testcase/addtopo/) 2-7_t0 ~/.password -e ptf_imagetag=lastest

![1-1](https://jian-hong-wu.github.io/blog/testcase/1-1.png)
![1-2](https://jian-hong-wu.github.io/blog/testcase/1-2.png)
![1-3](https://jian-hong-wu.github.io/blog/testcase/1-3.png)
![1-4](https://jian-hong-wu.github.io/blog/testcase/1-4.png)
![1-5](https://jian-hong-wu.github.io/blog/testcase/1-5.png)
![1-6](https://jian-hong-wu.github.io/blog/testcase/1-6.png)

#### b. deploy minigraph
//設定 inventory = lab， 指定測試機台 as5812-54x，名稱為 2-7_t0，產生並部署 minigraph

[ansible-playbook](https://jian-hong-wu.github.io/blog/testcase/playbook/) -i lab [config_sonic_basedon_testbed.yml](https://jian-hong-wu.github.io/blog/testcase/config_sonic_basedon_testbed/) -l as5812-54x -e testbed_name=2-7_t0 -e deploy=true -e save=true

![2-1](https://jian-hong-wu.github.io/blog/testcase/2-1.png)
![2-2](https://jian-hong-wu.github.io/blog/testcase/2-2.png)

#### c. run test
//testcase 檔案位於 ~/sonic-mgmt/ansible/roles/test/vars/testcases.yml，選擇執行 testcase 中的 syslog

ansible-playbook -i lab --limit as5812-54x test_sonic.yml -e testbed_name=2-7_t0 -e testcase_name=syslog -vvvv

![3-1](https://jian-hong-wu.github.io/blog/testcase/3-1.png)
![3-2](https://jian-hong-wu.github.io/blog/testcase/3-2.png)
![3-3](https://jian-hong-wu.github.io/blog/testcase/3-3.png)

//返回上一層並進入資料夾 tsets

cd ../tests

//用 py .test 執行測試 test_syslog.py 

py.test --inventory=lab --host-pattern=2-7_t0 --module-path ../ansible/library/ --testbed=2-7_t0 --testbed_file=../ansible/testbed.csv ./syslog/test_syslog.py --log-level=DEBUG -vvvv --show-capture=stdout --duration=0

![4-1](https://jian-hong-wu.github.io/blog/testcase/4-1.png)
![4-2](https://jian-hong-wu.github.io/blog/testcase/4-2.png)
![4-3](https://jian-hong-wu.github.io/blog/testcase/4-3.png)

#### d. remove topology
//返回上一層並進入資料夾 ansible

cd ../ansible

//移除 topology 2-7_t0

./testbed-cli.sh remove-topo 2-7_t0 ~/.password

//離開

exit

//刪除 container test

docker rm test

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
	
    -d <dir>         : sonic vm directory (default: /var/ubuntu/sonic-vm)

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
