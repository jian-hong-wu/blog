[上一頁](https://jian-hong-wu.github.io/blog/ONIE/)

# How to update ONIE on Accton Open Networking switch

1. Reboot the switch.
    1.1 type reboot if you are under sonic OS.   
    1.2 You will see the GRUB menu pops up.    
    
![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/1.png)

2. Select "ONIE: Update ONIE" menu item.   
 
![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/2.png)

3. $ onie-discovery-stop

![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/3.png)

4. You are in ONIIE, set the IP address in ONIE and try to ping your TFTP server. (Server IP: 192.168.40.24) TFTP server is the server that you have the ONIE image saved.    

    4.1 $ ifconfig   
![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/4.png)

5. Input "onie-self-update [TFTP location]" command and the upgrade will start.

$ onie-self-update tftp://192.168.40.24/onie-update-x86_64-accton_as6812

![](https://jian-hong-wu.github.io/blog/ONIE/onie_update/5.png)

Now, you have upgraded the ONIE image.
