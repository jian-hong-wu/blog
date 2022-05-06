# show

### change the port speed (Ethernet48 port to 40G, Ethernet2 to 10G)
```
admin@sonic:~$ show interfaces status Ethernet2
  Interface    Lanes    Speed    MTU    FEC          Alias    Vlan    Oper    Admin            Type    Asym PFC    Oper Speed
-----------  -------  -------  -----  -----  -------------  ------  ------  -------  --------------  ----------  ------------
  Ethernet2        4      25G   9100   none  Eth6/4(Port3)  routed    down       up  SFP/SFP+/SFP28         N/A           25G
admin@sonic:~$
admin@sonic:~$ # change the port speed to 1000G
admin@sonic:~$ sudo config interface speed Ethernet2 1000000

Can't set the port speed. Only support port speed: 25000.
admin@sonic:~$
admin@sonic:~$ # change the port speed to 10G
admin@sonic:~$ sudo config interface speed Ethernet2 10000

Due to the special circuit scheme on PCB of this device, the port specified
in the command is one of the child port out of 4 internally broken out ports.
To change port speed as 1G or 10G, you must use "config interface breakout"
command to change the port breakout mode as "4x10G[1G]". This will change
port speed as 10G upon 4 ports at the same time. Under "4x10G[1G]" breakout mode,
it is allowed to use "config interface speed" command to set port speed upon
any port out of those 4 ports as 1G or 10G.

admin@sonic:~$
admin@sonic:~$
admin@sonic:~$ show interfaces status Ethernet48
  Interface        Lanes    Speed    MTU    FEC            Alias    Vlan    Oper    Admin             Type    Asym PFC    Oper Speed
-----------  -----------  -------  -----  -----  ---------------  ------  ------  -------  ---------------  ----------  ------------
 Ethernet48  77,78,79,80     100G   9100   none  Eth49/1(Port49)  routed    down       up  QSFP28 or later         N/A          100G
admin@sonic:~$
admin@sonic:~$
admin@sonic:~$ sudo config interface speed Ethernet48 10000

Can't set the port speed. Only support port speed: 40000, 100000.
admin@sonic:~$ sudo config interface speed Ethernet48 40000
admin@sonic:~$ show interfaces status Ethernet48
  Interface        Lanes    Speed    MTU    FEC            Alias    Vlan    Oper    Admin             Type    Asym PFC    Oper Speed
-----------  -----------  -------  -----  -----  ---------------  ------  ------  -------  ---------------  ----------  ------------
 Ethernet48  77,78,79,80      40G   9100   none  Eth49/1(Port49)  routed      up       up  QSFP28 or later         N/A           40G
admin@sonic:~$
```
