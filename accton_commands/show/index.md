# show

### show logging | more
admin@sonic:~$ **show logging | more**  
```
admin@sonic:~$ show logging | more
Feb 18 02:32:36.096919 sonic INFO dhclient[2072]: DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 11
Feb 18 02:32:47.062646 sonic INFO dhclient[2072]: No DHCPOFFERS received.
Feb 18 02:32:47.063048 sonic INFO dhclient[2072]: No working leases in persistent database - sleeping.
Feb 18 02:34:11.174235 sonic INFO dhclient[2107]: XMT: Solicit on eth0, interval 115970ms.
Feb 18 02:36:07.230682 sonic INFO dhclient[2107]: XMT: Solicit on eth0, interval 122540ms.
Feb 18 02:38:09.871024 sonic INFO dhclient[2107]: XMT: Solicit on eth0, interval 123220ms.
Feb 18 02:39:34.678212 sonic INFO dhclient[2072]: DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 4
Feb 18 02:39:38.498219 sonic INFO dhclient[2072]: DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 6
Feb 18 02:39:44.489385 sonic INFO dhclient[2072]: DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 13
Feb 18 02:39:57.132521 sonic INFO dhclient[2072]: DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 16
Feb 18 02:40:13.190577 sonic INFO dhclient[2107]: XMT: Solicit on eth0, interval 124270ms.
Feb 18 02:40:13.818636 sonic INFO dhclient[2072]: DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 7
Feb 18 02:40:20.098623 sonic INFO dhclient[2072]: DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 8
Feb 18 02:40:28.294677 sonic INFO dhclient[2072]: DHCPDISCOVER on eth0 to 255.255.255.255 port 67 interval 7
Feb 18 02:40:35.543035 sonic INFO dhclient[2072]: No DHCPOFFERS received.
Feb 18 02:40:35.543440 sonic INFO dhclient[2072]: No working leases in persistent database - sleeping.
Feb 18 02:42:17.550441 sonic INFO dhclient[2107]: XMT: Solicit on eth0, interval 112640ms.
Feb 18 02:44:10.286634 sonic INFO dhclient[2107]: XMT: Solicit on eth0, interval 114810ms.
--More--
```

### show interfaces status | more
admin@sonic:~$ **show interfaces status | more**
```
admin@sonic:~$ show interfaces status | more
  Interface            Lanes    Speed    MTU    FEC            Alias    Vlan  Oper    Admin             Type    Asym PFC    Oper Speed
-----------  ---------------  -------  -----  -----  ---------------  ------  ------  -------  ---------------  ----------  ------------
  Ethernet0                3      25G   9100   none    Eth6/3(Port1)  routed  down       up              N/A         N/A           25G
  Ethernet1                2      25G   9100   none    Eth6/2(Port2)  routed  down       up              N/A         N/A           25G
  Ethernet2                4      25G   9100   none    Eth6/4(Port3)  routed  down       up   SFP/SFP+/SFP28         N/A           25G
  Ethernet3                8      25G   9100   none    Eth7/4(Port4)  routed  down       up              N/A         N/A           25G
  Ethernet4                7      25G   9100   none    Eth7/3(Port5)  routed  down     down              N/A         N/A           25G
  Ethernet5                1      25G   9100   none    Eth6/1(Port6)  routed  down       up              N/A         N/A           25G
  Ethernet6                5      25G   9100   none    Eth7/1(Port7)   trunk  down       up              N/A         N/A           25G
  Ethernet7               16      25G   9100   none   Eth11/4(Port8)   trunk  down       up              N/A         N/A           25G
  Ethernet8                6      25G   9100   none    Eth7/2(Port9)  routed  down       up              N/A         N/A           25G
  Ethernet9               14      25G   9100   none  Eth11/2(Port10)  routed  
  --More--
  
 Ethernet10               13      25G   9100   none  Eth11/1(Port11)  routed  down       up              N/A         N/A           25G
 Ethernet11               15      25G   9100   none  Eth11/3(Port12)  routed  down       up              N/A         N/A           25G
 Ethernet12               23      25G   9100   none  Eth18/3(Port13)  routed  down       up   SFP/SFP+/SFP28         N/A           25G
 Ethernet13               22      25G   9100   none  Eth18/2(Port14)  routed  down       up              N/A         N/A           25G
 Ethernet14               24      25G   9100   none  Eth18/4(Port15)  routed  down       up              N/A         N/A           25G
 Ethernet15               32      25G   9100   none  Eth19/4(Port16)  routed  down       up   SFP/SFP+/SFP28         N/A           25G
 Ethernet16               31      25G   9100   none  Eth19/3(Port17)  routed  down       up              N/A         N/A           25G
 Ethernet17               21      25G   9100   none  Eth18/1(Port18)  routed  down       up              N/A         N/A           25G
 Ethernet18               29      25G   9100   none  Eth19/1(Port19)  routed  down       up   SFP/SFP+/SFP28         N/A           25G
 Ethernet19               36      25G   9100   none  Eth23/4(Port20)  routed  down       up              N/A         N/A           25G
 Ethernet20               30      25G   9100   none  Eth19/2(Port21)  routed  down       up              N/A         N/A           25G
--More--

 Ethernet46               72      25G   9100   none  Eth44/4(Port47)  routed  down       up              N/A         N/A           25G
 Ethernet47               70      25G   9100   none  Eth44/2(Port48)  routed  down       up              N/A         N/A           25G
 Ethernet48      77,78,79,80     100G   9100   none  Eth49/1(Port49)  routed  down       up  QSFP28 or later         N/A          100G
 Ethernet52      85,86,87,88     100G   9100   none  Eth50/1(Port50)   trunk  down       up              N/A         N/A          100G
 Ethernet56      93,94,95,96     100G   9100   none  Eth51/1(Port51)  routed  down       up  QSFP28 or later         N/A          100G
 Ethernet60     97,98,99,100     100G   9100   none  Eth52/1(Port52)  routed  down       up              N/A         N/A          100G
 Ethernet64  105,106,107,108     100G   9100   none  Eth53/1(Port53)  routed  down       up              N/A         N/A          100G
 Ethernet68  113,114,115,116     100G   9100   none  Eth54/1(Port54)  routed  down       up              N/A         N/A          100G
 Ethernet72  121,122,123,124     100G   9100   none  Eth55/1(Port55)  routed  down       up              N/A         N/A          100G
 Ethernet76  125,126,127,128     100G   9100   none  Eth56/1(Port56)  routed  down       up              N/A         N/A          100G
admin@sonic:~$  
```

### show interfaces transceiver presence | more
admin@sonic:~$ **show interfaces transceiver presence | more**
```
admin@sonic:~$ show interfaces transceiver presence | more
Port        Presence
----------  -----------
Ethernet0   Not present
Ethernet1   Not present
Ethernet2   Present
Ethernet3   Not present
Ethernet4   Not present
Ethernet5   Not present
Ethernet6   Not present
Ethernet7   Not present
Ethernet8   Not present
Ethernet9   Not present
Ethernet10  Not present
Ethernet11  Not present
Ethernet12  Present
Ethernet13  Not present
Ethernet14  Not present
Ethernet15  Present
Ethernet16  Not present
Ethernet17  Not present
Ethernet18  Present
Ethernet19  Not present
Ethernet20  Not present
--More--

Ethernet44  Not present
Ethernet45  Not present
Ethernet46  Not present
Ethernet47  Not present
Ethernet48  Present
Ethernet52  Not present
Ethernet56  Present
Ethernet60  Not present
Ethernet64  Not present
Ethernet68  Not present
Ethernet72  Not present
Ethernet76  Not present
admin@sonic:~$
```

### show interfaces transceiver
admin@sonic:~$ **show interfaces transceiver**
```
admin@sonic:~$ show interfaces transceiver
Usage: show interfaces transceiver [OPTIONS] COMMAND [ARGS]...

  Show SFP Transceiver information

Options:
  -?, -h, --help  Show this message and exit.

Commands:
  eeprom    Show interface transceiver EEPROM information
  lpmode    Show interface transceiver low-power mode status
  presence  Show interface transceiver presence
admin@sonic:~$ show interfaces transceiver presence
```

### show interfaces
admin@sonic:~$ **show interfaces**
```
admin@sonic:~$ show interfaces
Usage: show interfaces [OPTIONS] COMMAND [ARGS]...

  Show details of the network interfaces

Options:
  -?, -h, --help  Show this message and exit.

Commands:
  alias        Show Interface Name/Alias Mapping
  autoneg      Show interface autoneg information
  breakout     Show Breakout Mode information by interfaces
  counters     Show interface counters
  description  Show interface status, protocol and description
  diagnostic   Show diagnostic cable test information
  naming_mode  Show interface naming_mode status
  neighbor     Show neighbor related information
  portchannel  Show PortChannel information
  status       Show Interface status information
  transceiver  Show SFP Transceiver information
admin@sonic:~$
```


