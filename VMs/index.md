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

---

[ Root Cause ]
當我們在嘗試建立 VM 時, 下指令 “./testbed-cli.sh start-vms server_1 password.txt”  
testbed-cli.sh 會去開啟一些設定檔, 並建立相關的東西, 包括 :  
1.  create “br-VM01xx-x” interfaces (depends on the definition in sonic-mgmt/ansible/veos)  
ð You can use “ifconfig” to check.
2.  several tasks “qemu-system-x86” are also created and they will occupy 127.0.0.1:7000 ~ 7004  
ð You can use “sudo ss -tulpn | grep 7000” to check. It looks like :  
tcp   LISTEN  0       1     127.0.0.1:7000      0.0.0.0:*     users:(("qemu-system-x86",pid=515278,fd=9))
 
前面幾次失敗的執行, 已經建立相關的 task 把 ports 都占滿了
 
[ Solution ]  
1.  You can use “top” command to check this task.  
2.  Kill those “qemu-system-x86” tasks to release related ports.  
$ sudo kill 515278
 
這會引發一個問題 : 如果 A 在 server 上建立 VMs, 是否代表 B 就不能建 ?  
不然 ports 會衝突…… ??
