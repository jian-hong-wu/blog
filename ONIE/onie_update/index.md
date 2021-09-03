[上一頁](https://jian-hong-wu.github.io/blog/ONIE/)

How to update ONIE on Edgecore x86 platform switch

Reboot the data center.

![](https://jian-hong-wu.github.io/blog/ONIE/1.png)

Enter the "ONIE: Update ONIE" mode.
 
![](https://jian-hong-wu.github.io/blog/ONIE/2.png)

$ onie-discovery-stop

![](https://jian-hong-wu.github.io/blog/ONIE/3.png)

Set the IP address in ONIE and try to ping the TFTP server. (Server IP: 192.168.40.24)

$ ifconfig

![](https://jian-hong-wu.github.io/blog/ONIE/4.png)

Input "onie-self-update [TFTP location]" command and the upgrade will start.

$ onie-self-update tftp://192.168.40.24/onie-update-x86_64-accton_as6812

![](https://jian-hong-wu.github.io/blog/ONIE/5.png)
