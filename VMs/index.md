[上一頁](https://jian-hong-wu.github.io/blog/)

## 建立 VMs

在 192.168.40.25 這台 server 上 :  
[ sonic-mgmt ]  
in /home/jlo/sonic/src/202012_latest/sonic-mgmt  
以後有檔案更改, 都是放在這邊

[ VM related images ]  
In /home/jlo/sonic/src/202012_latest/veos-vm

[ Creating container ]  
In /home/jlo/sonic/src/202012_latest, type :  
  $ docker run --name WORK-JLO -v $PWD:/data -it sonic-mgmt-dev

(1)   原本的 container name “WORK” 可以改成自己想要的名字  
(2)   使用的 image 是 sonic-mgmt-dev:latest  
(3)   進入 container 以後, server 上的目錄 /home/jlo, 會被 mapping 到 container 的 /data

[ Create VMs ]  

(in the container)  
/# cd /data/sonic-mgmt/ansible  
/# ./testbed-cli.sh start-vms server_1 password.txt

[ Ping VMs ]  

(in the container)  
/# ansible -m ping -i veos server_1

(In the server)   10.250.1.100 ~ 10.250.1.167  
$ ping 10.250.1.100

 

[ Stop VMs ]  

(in the container)  
/# ./testbed-cli.sh stop-vms server_1 ~/.password  
(those interfaces “br-VM01xx-x” still exist and need extra commands to remove)
