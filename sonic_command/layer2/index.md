[上一頁](https://jian-hong-wu.github.io/blog/sonic_command/)

# Layer 2 commands

$ show arp 

![](https://jian-hong-wu.github.io/blog/sonic_command/layer2/1.png)

or  
$ cat /proc/net/arp 

![](https://jian-hong-wu.github.io/blog/sonic_command/layer2/1.1.png)

$ sudo config vlan add 1200  
$ sudo config vlan member add 1200 Ethernet1  
$ sudo config vlan member add 1200 Ethernet9 -u  
$ sudo config vlan member add 1200 Ethernet8  
$ show vlan config

![](https://jian-hong-wu.github.io/blog/sonic_command//layer2/2.png)

$ show interfaces portchannel

![](https://jian-hong-wu.github.io/blog/sonic_command//layer2/3.png)

$ show lldp table

![](https://jian-hong-wu.github.io/blog/sonic_command//layer2/4.png)

$ show lldp neighbors

![](https://jian-hong-wu.github.io/blog/sonic_command//layer2/5.png)

$ show lldp neighbors eth0

![](https://jian-hong-wu.github.io/blog/sonic_command//layer2/6.png)
