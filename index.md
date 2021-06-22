#  Hong's Blog

## 目錄
       
   1. [How to create a blog like this!](https://jian-hong-wu.github.io/blog/createblog/)
   2. [testcase](https://jian-hong-wu.github.io/blog/testcase/)
   3. [testbed-cli.sh的說明文件](https://jian-hong-wu.github.io/blog/testbed-cli.sh)
   4. [常用的docker指令](https://jian-hong-wu.github.io/blog/docker/)
   5. [常用的shell指令](https://jian-hong-wu.github.io/blog/shell/)
   6. [安裝puttyz的方法](https://jian-hong-wu.github.io/blog/putty/)
   7. [jenkins安裝指令](https://jian-hong-wu.github.io/blog/jenkins/)
   8. [VScode安裝指令](https://jian-hong-wu.github.io/blog/VScode/)




## How to create a blog like this!

1. sign in github

2. create a new repository

3. find "GitHub Pages" in settings

4. choose a theme

5. edit the file "index.md" to add content

6. find the URL in "GitHub Pages" in settings

#### 參考：

[如何在 Github Pages 建立靜態網站](https://www.youtube.com/watch?v=bU0f1IvUcZA)

## testcase

在終端輸入以下指令

docker run -it --name test docker-sonic-mgmt bash

cd sonic-mgmt/

cd server_config

./server.sh 2

cd ../ansible/

vi testbed.csv

./testbed-cli.sh -b VM0200 add-topo 2-7_t0 ~/.password -e ptf_imagetag=lastest

ansible-playbook -i lab config_sonic_basedon_testbed.yml -l as5812-54x -e testbed_name=2-7_t0 -e deploy=true -e save=true

ansible-playbook -i lab --limit as5812-54x test_sonic.yml -e testbed_name=2-7_t0 -e testcase_name=syslog -vvvv

cd ../tests

py.test --inventory=lab --host-pattern=2-7_t0 --module-path ../ansible/library/ --testbed=2-7_t0 --testbed_file=../ansible/testbed.csv ./syslog/test_syslog.py --log-level=DEBUG -vvvv --show-capture=stdout --duration=0

cd ../ansible

./testbed.cli.sh remove-topo 2-7_t0 ~/.password

exit

docker rm test

--測試結束

## testbed-cli.sh的說明文件

   testbed-cli. Interface to testbeds

Usage:

    ./testbed-cli.sh [options] (start-vms | stop-vms) <server-name> <vault-password-file>    
    ./testbed-cli.sh [options] (start-topo-vms | stop-topo-vms) <topo-name> <vault-password-file>    
    ./testbed-cli.sh [options] (add-topo | remove-topo | renumber-topo | connect-topo) <topo-name> <vault-password-file>    
    ./testbed-cli.sh [options] refresh-dut <topo-name> <vault-password-file>    
    ./testbed-cli.sh [options] (connect-vms | disconnect-vms) <topo-name> <vault-password-file>    
    ./testbed-cli.sh [options] config-vm <topo-name> <vm-name> <vault-password-file>    
    ./testbed-cli.sh [options] (gen-mg | deploy-mg | test-mg) <topo-name> <inventory> <vault-password-file>    
    ./testbed-cli.sh [options] (create-master | destroy-master) <k8s-server-name> <vault-password-file>

Options:

    -t <tbfile>     : testbed CSV file name (default: 'testbed.csv')    
    -m <vmfile>     : virtual machine file name (default: 'veos')    
    -k <vmtype>     : vm type (veos|ceos) (default: 'veos')    
    -n <vm_num>     : vm num (default: 0)    
    -b <vmbase>     : Specify the VM Base ID the format is VM0100, VM0201 (default: parsing from testbed.csv)    
    -s <msetnumber> : master set identifier on specified <k8s-server-name> (default: 1)    
    -d <dir>        : sonic vm directory (default: /var/ubuntu/sonic-vm)
    
Positional Arguments:

    <server-name>         : Hostname of server on which to start VMs    
    <vault-password-file> : Path to file containing Ansible Vault password    
    <topo-name>           : Name of the target topology    
    <inventory>           : Name of the Ansible inventory containing the DUT    
    <k8s-server-name>     : Server identifier in form k8s_server_{id}, corresponds to k8s_ubuntu inventory group name    
    <vmbase>              : Specify the VM base ID and the format is VM01xx or VM02xx (xx = 01~63, default: parsing from testbed.csv)    
                  Cost of VMs  0VM    4VMs      6VMs   8VMs        24VMs      32VMs  64VMs                  
                  Topologies   ptf32  t0        t0-16  t0-56       t1-lag     t1     t1-64                  
                               ptf64  t0-64            t1-8vm      t1-64-lag                               
                                      t0-64-32         t1-8vm-lag                                      
                                      t0-52                                      
                                      t0-116

To start all VMs on a server: ./testbed-cli.sh start-vms 'server-name' ~/.password

To restart a subset of VMs:

        ./testbed-cli.sh start-vms server-name vault-password-file -e respin_vms=[vm_list]        
             vm_list is separated by comma and shouldn't have space in the list.             
                 e.g., respin_vms=[VM0310,VM0330]
                 
To pause some time after triggered starting of a batch of VMs:

        ./testbed-cli.sh start-vms server-name vault-password-file -e batch_size=2 -e interval=60
        
To enable autostart of VMs:

        ./testbed-cli.sh start-vms server-name vault-password-file -e autostart=yes
        
To start VMs for specified topology on server: ./testbed-cli.sh start-topo-vms 'topo-name' ~/.password

To stop all VMs on a server:  ./testbed-cli.sh stop-vms 'server-name' ~/.password

To stop VMs for specified topology on server: ./testbed-cli.sh stop-topo-vms 'topo-name' ~/.password

To deploy a topology on a server: ./testbed-cli.sh add-topo 'topo-name' ~/.password

    Optional argument for add-topo:    
        -e ptf_imagetag=<tag>    # Use PTF image with specified tag for creating PTF container
        
To remove a topology on a server: ./testbed-cli.sh remove-topo 'topo-name' ~/.password

To renumber a topology on a server: ./testbed-cli.sh renumber-topo 'topo-name' ~/.password

To connect a topology: ./testbed-cli.sh connect-topo 'topo-name' ~/.password

To refresh DUT in a topology: ./testbed-cli.sh refresh-dut 'topo-name' ~/.password

To configure a VM on a server: ./testbed-cli.sh config-vm 'topo-name' 'vm-name' ~/.password

To generate minigraph for DUT in a topology: ./testbed-cli.sh gen-mg 'topo-name' 'inventory' ~/.password

To deploy minigraph to DUT in a topology: ./testbed-cli.sh deploy-mg 'topo-name' 'inventory' ~/.password

    gen-mg, deploy-mg, test-mg supports enabling/disabling data ACL with parameter    
        -e enable_data_plane_acl=true        
        -e enable_data_plane_acl=false        
        by default, data acl is enabled
        
To create Kubernetes master on a server: ./testbed-cli.sh -m k8s_ubuntu create-master 'k8s-server-name'  ~/.password

To destroy Kubernetes master on a server: ./testbed-cli.sh -m k8s_ubuntu destroy-master 'k8s-server-name' ~/.password

#### 參考：

https://github.com/Azure/sonic-mgmt

## 安裝puttyz的方法

sudo apt-get install putty

#### 參考:

https://www.itread01.com/p/122712.html

## VScode安裝指令

請透過瀏覽器連到下方網址

https://code.visualstudio.com/download

點選 Debian, Ubuntu

移動路徑到所下載 VS Code 的安裝檔所在位置

在終端機中輸入下方指令

sudo dpkg -i 下載的安裝檔名稱

請在終端機中輸入下方指令

code

#### 參考：

https://learningsky.io/tools-ubuntu-install-visual-studio-code/

## jenkins安裝指令

先安裝java:

sudo apt-get update

sudo apt-get upgrade

sudo apt-get install default-jdk

javac -version   (測試)

安裝jenkin:

wget -q -O - https://jenkins-ci.org/debian/jenkins-ci.org.key | sudo apt-key add -  

sudo sh -c 'echo deb http://pkg.jenkins-ci.org/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'  

sudo apt-get update

sudo apt-get install jenkins  

執行jenkin:

sudo service jenkins start  

開啟 Jenkins 網頁頁面 http://yourserverIP:8080

出現畫面後需要取得初始的 admin 密碼

sudo cat /var/lib/jenkins/secrets/initialAdminPassword  

輸入完密碼後即可選擇安裝所需的插件，系統會自動安裝建議的套件

#### 參考:

https://oranwind.org/-devops-jenkins-yu-centos-ubuntu-an-zhuang-jiao-xue/


## I have learned 
   1. [Git GitHub GitLab使用教程](https://www.youtube.com/watch?v=usgghEA_BEk&list=PL5eFspCU9xDe4Gz0LotCdRg5V68AD3icH&index=1)
   2. [尚硅谷 Docker教學](https://www.youtube.com/watch?v=37b3cWIIxUg&list=PLmOn9nNkQxJFX0YVLDw5EMUL-4cVzXL33&index=1)
   3. [Docker入门教学](https://www.youtube.com/watch?v=bumV64OfLCs&list=PLliocbKHJNwubNT2oK-xlB1GXTXuLFb0I)
   4. [Docker教學 - 入門介紹](https://www.youtube.com/watch?v=pa1Zao1Hy2c&list=PLVVMQF8vWNCJnlO0Y34AE_1AgCapldp38)
   5. [Ubuntu 入門](https://www.youtube.com/watch?v=u6-IMozWQG0&list=PLkmkNssEXKuxfpeezLrnmHsUoJRJzWVui&index=1)
   6. [Jenkins 教學](https://www.youtube.com/watch?v=SbMabIXQd_A&list=PLmOn9nNkQxJE_3wrOfHdL1dWRY6CCHBnh)
