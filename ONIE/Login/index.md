[上一頁](https://jian-hong-wu.github.io/blog/ONIE/)

用瀏覽器登入 192.168.40.61 開啟指定機器

![](https://jian-hong-wu.github.io/blog/ONIE/Login/12.png)

//連到機器輸入帳密  
$ telnet 192.168.40.50  
![](https://jian-hong-wu.github.io/blog/ONIE/Login/1.png)

![](https://jian-hong-wu.github.io/blog/ONIE/Login/3.png)

選擇 4. Port Access

![](https://jian-hong-wu.github.io/blog/ONIE/Login/4.png)

選擇指定機器並登入

![](https://jian-hong-wu.github.io/blog/ONIE/Login/7.png)

//重新啟動
$ reboot

![](https://jian-hong-wu.github.io/blog/ONIE/Login/8.png)

![](https://jian-hong-wu.github.io/blog/ONIE/Login/10.png)

選擇 ONIE

![](https://jian-hong-wu.github.io/blog/ONIE/Login/11.png)

ONIE: Install OS
---
<pre>4..3..2..1..Info: eth0:  Checking link... down.
ONIE: eth0: link down.  Skipping configuration.
ONIE: Failed to configure eth0 interface
ONIE: Starting ONIE Service Discovery
Info: Attempting tftp://onie-server/1c-ea-0b-84-78-00/onie-installer-x86_64-accton_as7816_64x-r0 ...
Info: Attempting tftp://onie-server/onie-installer-x86_64-accton_as7816_64x-r0 ...
Info: Attempting tftp://onie-server/onie-installer-x86_64-accton_as7816_64x-r0.bin ...
Info: Attempting tftp://onie-server/onie-installer-x86_64-accton_as7816_64x ...
Info: Attempting tftp://onie-server/onie-installer-x86_64-accton_as7816_64x.bin ...
Info: Attempting tftp://onie-server/onie-installer-accton_as7816_64x ...
Info: Attempting tftp://onie-server/onie-installer-accton_as7816_64x.bin ...
Info: Attempting tftp://onie-server/onie-installer-x86_64-bcm ...
Info: Attempting tftp://onie-server/onie-installer-x86_64-bcm.bin ...
Info: Attempting tftp://onie-server/onie-installer-x86_64 ...
Info: Attempting tftp://onie-server/onie-installer-x86_64.bin ...
Info: Attempting tftp://onie-server/onie-installer ...
Info: Attempting tftp://onie-server/onie-installer.bin ...
Info: Sleeping for 20 seconds 
4..3..2..1..Info: eth0:  Checking link... down.
</pre>
---
