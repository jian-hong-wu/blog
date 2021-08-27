[上一頁](/blog/sonic_command/layer2/show/)

show commands (misc)


$ show arp 
<pre>admin@sonic:~$ show arp
Address    MacAddress    Iface    Vlan
---------  ------------  -------  ------
Total number of entries 0 
admin@sonic:~$ 
</pre>

<pre>admin@sonic:~$ show arp
Error fetching Neighbors: /bin/sh: /usr/sbin/arp: not found

admin@sonic:~$ 
</pre>

or  
$ cat /proc/net/arp 

![](/blog/sonic_command/layer2/1.1.png)

$ sudo config vlan add 1200  
$ sudo config vlan member add 1200 Ethernet1  
$ sudo config vlan member add 1200 Ethernet9 -u  
$ sudo config vlan member add 1200 Ethernet8  
$ show vlan config

![](/blog/sonic_command//layer2/2.png)

$ show interfaces portchannel

![](/blog/sonic_command//layer2/3.png)

$ show lldp table

![](/blog/sonic_command//layer2/4.png)

$ show lldp neighbors

![](/blog/sonic_command//layer2/5.png)

$ show lldp neighbors eth0

![](/blog/sonic_command//layer2/6.png)
