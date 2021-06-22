#  Hong's Blog

### 目錄
       
   1. [How to create a blog like this!](https://jian-hong-wu.github.io/blog/createblog/)
   2. [testcase](https://jian-hong-wu.github.io/blog/testcase/)
   3. [常用的docker指令](https://jian-hong-wu.github.io/blog/docker/)
   4. [常用的shell指令](https://jian-hong-wu.github.io/blog/shell/)
   5. [putty安裝指令](https://jian-hong-wu.github.io/blog/putty/)
   6. [jenkins安裝指令](https://jian-hong-wu.github.io/blog/jenkins/)
   7. [VScode安裝指令](https://jian-hong-wu.github.io/blog/VScode/)
   8. [testbed-cli.sh 的說明文件](https://jian-hong-wu.github.io/blog/testbed-cli/)



### testbed-cli.sh 的說明文件

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

   
### I have learned 
   1. [Git GitHub GitLab使用教程](https://www.youtube.com/watch?v=usgghEA_BEk&list=PL5eFspCU9xDe4Gz0LotCdRg5V68AD3icH&index=1)
   2. [尚硅谷 Docker教學](https://www.youtube.com/watch?v=37b3cWIIxUg&list=PLmOn9nNkQxJFX0YVLDw5EMUL-4cVzXL33&index=1)
   3. [Docker入门教学](https://www.youtube.com/watch?v=bumV64OfLCs&list=PLliocbKHJNwubNT2oK-xlB1GXTXuLFb0I)
   4. [Docker教學 - 入門介紹](https://www.youtube.com/watch?v=pa1Zao1Hy2c&list=PLVVMQF8vWNCJnlO0Y34AE_1AgCapldp38)
   5. [Ubuntu 入門](https://www.youtube.com/watch?v=u6-IMozWQG0&list=PLkmkNssEXKuxfpeezLrnmHsUoJRJzWVui&index=1)
   6. [Jenkins 教學](https://www.youtube.com/watch?v=SbMabIXQd_A&list=PLmOn9nNkQxJE_3wrOfHdL1dWRY6CCHBnh)
