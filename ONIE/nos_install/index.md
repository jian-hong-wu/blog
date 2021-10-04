[上一頁](https://jian-hong-wu.github.io/blog/ONIE/)

# How to install NOS on Accton Open Networking switch

1. Reboot the switch.
    1.1 type reboot if you are under sonic OS.   
    1.2 You will see the GRUB menu pops up.    
    
![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/1.png)

2. Select "ONIE: Install ONIE" menu item.   
 
![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/2.png)

3. $ onie-discovery-stop

![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/3.png)

4. You are in ONIE, set the IP address in ONIE and try to ping your TFTP server. (Server IP: 192.168.40.24) TFTP server is the server that you have the ONIE image saved.    

    4.1 $ ifconfig   
![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/4.png)

5. Input "onie-nos-install sonic-broadcom.bin" command and the install will start.

$ onie-nos-install sonic-broadcom.bin

![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/5.png)

Now, you have install the sonic NOS.

