

鏈路聚合：兩個網絡卡邦在一起
balance-rr 輪循  任務輪流來  增快傳輸速率
active-backup  只是自己當作備用  使介面更穩定

ping不通還需要物理裝置的支援
bond-slave  為bond介面服務 需要兩個介面 因為兩個網絡卡

操作命令
nmcli connection add con-name bond0 ifname bond0 type bond mode active-backup ip4 172.25.254.213/24
 
這時候會自動生成  /proc/net/bonding/bond0
採用  watch -n 1 cat /proc/net/bonding/bond0
這裡是先加一個連線bond型別  
下面新增兩塊網絡卡

nmcli connection add con-name eth0 ifname eth0 type bond-slave master bond0
nmcli connection add con-name eth1 ifname eth1 type bond-slave master bond0  
因為是slave 所以得有主人 master 

這時候
ifconfig down  eth0  或者 eth1   還會可以ping通
ifconfig up eth1 就恢復了
你只有用真機ping虛擬機器才行  


nmcli connection delete eth1
nmcli connection delete eth0
nmcli connection delete bond0
nmcli connection show 
就刪掉了

/etc/sysconfig/network-scripts
文字形式新增ifcfg-bond0

DEVICE=bond0
ONBOOT=yes
BOOTPROTO=none
IPADDR=172.25.254.100
NETMASK=255.255.255.0
TYPE=Bond
BONDING_OPTS=mode=active-backup

新增檔案  ifcfg-eth1  ifcfg-eth0
DEVICE=eth0
ONBOOT=yes
BOOTPROTO=none
MASTER=bond0


DEVICE=eth1
ONBOOT=yes
BOOTPROTO=none
MASTER=bond0


然後systelclt restart network

以上都是鏈路聚合中的bonding

紅帽還出了 team鏈路聚合

team  
支援負載均衡（）
 雜湊加密
bond 不支援加密  不支援負載均衡  不支援雜湊加密

下面是team的操作
team是純軟體  
 
nmcli connectiong add con-name team0 ifname team0 type team \ config '{"runner":{"name":"activebackup"}}'  ip4 172.25.254.213/24
檢視狀態
watch -n 1 teamdctl team0  stat
新增網絡卡
nmcli connection add con-name eth0 ifname eth0 type team-slave master team0
nmcli connection add con-name eth1 ifname eth1 type team-slave master team0


檔案格式新增
DEVICE=team0
TEAM_CONFG="{\"runner\":{\"name\":\"activebackup\"}}"
DEVICETYPE=Team
BOOTPROTO=none
IPADDR=172.25.254.213
PREFIX=24
NAME=team0
ONBOOT=yes

DEVICE=eth0 
BOOTPROTO=none
ONBOOT=yes
TEAM_MASTER=team0
DEVICETYPE=TeanPort


DEVICE=eth1 
BOOTPROTO=none
ONBOOT=yes
TEAM_MASTER=team0
DEVICETYPE=TeanPort

不可以將DEVICETYPE  換為TYPE


 
/etc/sysconfig/network-scripts
vim  ifcfg-enp0s25

DEVICE=enp0s25
ONBOOT=yes
BOOTPROTO=none
IPADDR=172.25.254.13
NETMASK=255.255.255.0

nat地址轉換 會影響速度和核心負載  降低真實主機速度

橋接
可以讓虛擬機器通過核心直接連線網絡卡
網橋  虛擬機器直接通過真實網絡卡，設定的ip 和真機是同等級別

首先修改
/etc/sysconfig/network-scripts/
vim ifcfg-enp0s25

DEVICE=enp0s25
ONBOOT=yes
BOOTPROTO=none
BRIDGE=br0   br0名字後的數字隨意


然後建立br0橋

DEVICE=br0
ONBOOT=yes
BOOTPROTO=none
IPADDR=172.25.254.13
NETMASK=255.255.255.0
TYPE=Bridge


重啟網路就可以了

恢復的時候  刪除br0  修改enp0s25


DEVICE=enp0s25
ONBOOT=yes
BOOTPROTO=none
IPADDR=172.25.254.13
NETMASK=255.255.255.0


重啟網路即可


命令方式新增橋接

brctl addbr br0
ifconfig br0 172.25.254.13/24
brctl addif br0 eth0
brctl show


刪除橋的操作

ficonfig br0 down 
brctl delif br0 eth0
brctl delbr br0
brctl  show
