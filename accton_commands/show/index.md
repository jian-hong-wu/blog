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

### show interfaces status Ethernet2
admin@sonic:~$ **show interfaces status Ethernet2**
```
admin@sonic:~$ show interfaces status Ethernet2
  Interface    Lanes    Speed    MTU    FEC          Alias    Vlan    Oper    Admin            Type    Asym PFC    Oper Speed
-----------  -------  -------  -----  -----  -------------  ------  ------  -------  --------------  ----------  ------------
  Ethernet2        4      25G   9100   none  Eth6/4(Port3)  routed    down       up  SFP/SFP+/SFP28         N/A           25G
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

### show interfaces transceiver presence Ethernet2
admin@sonic:~$ **show interfaces transceiver presence Ethernet2**
```
admin@sonic:~$ show interfaces transceiver presence Ethernet2
Port       Presence
---------  ----------
Ethernet2  Present
admin@sonic:~$
```
### show interfaces transceiver lpmode ?
admin@sonic:~$ **show interfaces transceiver lpmode ?**
```
admin@sonic:~$ show interfaces transceiver lpmode ?
Error: invalid port '?'

Valid values for port: ['Ethernet0', 'Ethernet1', 'Ethernet2', 'Ethernet3', 'Ethernet4', 'Ethernet5', 'Ethernet6', 'Ethernet7', 'Ethernet8', 'Ethernet9', 'Ethernet10', 'Ethernet11', 'Ethernet12', 'Ethernet13', 'Ethernet14', 'Ethernet15', 'Ethernet16', 'Ethernet17', 'Ethernet18', 'Ethernet19', 'Ethernet20', 'Ethernet21', 'Ethernet22', 'Ethernet23', 'Ethernet24', 'Ethernet25', 'Ethernet26', 'Ethernet27', 'Ethernet28', 'Ethernet29', 'Ethernet30', 'Ethernet31', 'Ethernet32', 'Ethernet33', 'Ethernet34', 'Ethernet35', 'Ethernet36', 'Ethernet37', 'Ethernet38', 'Ethernet39', 'Ethernet40', 'Ethernet41', 'Ethernet42', 'Ethernet43', 'Ethernet44', 'Ethernet45', 'Ethernet46', 'Ethernet47', 'Ethernet48', 'Ethernet52', 'Ethernet56', 'Ethernet60', 'Ethernet64', 'Ethernet68', 'Ethernet72', 'Ethernet76']
admin@sonic:~$
```
### show interfaces transceiver lpmode [port]
```
admin@sonic:~$ show interfaces transceiver lpmode Ethernet76
Port        Low-power Mode
----------  ----------------
Ethernet76  Off
admin@sonic:~$ show interfaces transceiver lpmode Ethernet75
Error: invalid port 'Ethernet75'

Valid values for port: ['Ethernet0', 'Ethernet1', 'Ethernet2', 'Ethernet3', 'Ethernet4', 'Ethernet5', 'Ethernet6', 'Ethernet7', 'Ethernet8', 'Ethernet9', 'Ethernet10', 'Ethernet11', 'Ethernet12', 'Ethernet13', 'Ethernet14', 'Ethernet15', 'Ethernet16', 'Ethernet17', 'Ethernet18', 'Ethernet19', 'Ethernet20', 'Ethernet21', 'Ethernet22', 'Ethernet23', 'Ethernet24', 'Ethernet25', 'Ethernet26', 'Ethernet27', 'Ethernet28', 'Ethernet29', 'Ethernet30', 'Ethernet31', 'Ethernet32', 'Ethernet33', 'Ethernet34', 'Ethernet35', 'Ethernet36', 'Ethernet37', 'Ethernet38', 'Ethernet39', 'Ethernet40', 'Ethernet41', 'Ethernet42', 'Ethernet43', 'Ethernet44', 'Ethernet45', 'Ethernet46', 'Ethernet47', 'Ethernet48', 'Ethernet52', 'Ethernet56', 'Ethernet60', 'Ethernet64', 'Ethernet68', 'Ethernet72', 'Ethernet76']
admin@sonic:~$
admin@sonic:~$ show interfaces transceiver lpmode | more
Port        Low-power Mode
----------  ----------------
Ethernet0   Off
Ethernet1   Off
Ethernet2   Off
Ethernet3   Off
Ethernet4   Off
Ethernet5   Off
Ethernet6   Off
Ethernet7   Off
Ethernet8   Off
Ethernet9   Off
Ethernet10  Off
Ethernet11  Off
Ethernet12  Off
Ethernet13  Off
Ethernet14  Off
Ethernet15  Off
Ethernet16  Off
Ethernet17  Off
Ethernet18  Off
Ethernet19  Off
Ethernet20  Off
--More--

Ethernet44  Off
Ethernet45  Off
Ethernet46  Off
Ethernet47  Off
Ethernet48  Off
Ethernet52  Off
Ethernet56  Off
Ethernet60  Off
Ethernet64  Off
Ethernet68  Off
Ethernet72  Off
Ethernet76  Off
admin@sonic:~$
```
### show interfaces transceiver eeprom

```
admin@sonic:~$ show interfaces transceiver eeprom ?
?: SFP EEPROM Not detected
admin@sonic:~$ show interfaces transceiver eeprom Ethernet52
Ethernet52: SFP EEPROM Not detected
admin@sonic:~$
admin@sonic:~$ show interfaces transceiver eeprom Ethernet12
Ethernet12: SFP EEPROM detected
        Application Advertisement: N/A
        Connector: CopperPigtail
        DOM Capability:
                sff8472_dom_support: no
        Encoding: Unspecified
        Extended Identifier: GBIC/SFP defined by twowire interface ID
        Extended RateSelect Compliance: Unspecified
        Identifier: SFP/SFP+/SFP28
        LengthOM3(UnitsOf10m): 0
        Nominal Bit Rate(100Mbs): 255
        Specification compliance:
                SFP+CableTechnology: Passive Cable
        Vendor Date Code(YYYY-MM-DD Lot): 2021-11-01
        Vendor Name: Edgecore
        Vendor OUI: 70-72-cf
        Vendor PN: ET7402-25DAC-1M
        Vendor Rev: 01
        Vendor SN: J12045200001
admin@sonic:~$
admin@sonic:~$ show interfaces transceiver eeprom Ethernet56
Ethernet56: SFP EEPROM detected
        Application Advertisement: N/A
        Connector: No separable connector
        DOM Capability:
                Rx_power_support: no
                Temp_support: no
                Tx_power_support: no
                Voltage_support: no
        Encoding: Unspecified
        Extended Identifier: Power Class 1(1.5W max)
        Extended RateSelect Compliance: QSFP+ Rate Select Version 1
        Identifier: QSFP28 or later
        Length Cable Assembly(m): 1
        Nominal Bit Rate(100Mbs): 255
        Specification compliance:
        Vendor Date Code(YYYY-MM-DD Lot): 2017-06-28
        Vendor Name: Edgecore
        Vendor OUI: 70-72-cf
        Vendor PN: ET7402-100DAC-1M
        Vendor Rev: 01
        Vendor SN: J11917004024
admin@sonic:~$
admin@sonic:~$ show interfaces transceiver eeprom | more
Ethernet0: SFP EEPROM Not detected

Ethernet1: SFP EEPROM Not detected

Ethernet2: SFP EEPROM detected
        Application Advertisement: N/A
        Connector: CopperPigtail
        DOM Capability:
                sff8472_dom_support: no
        Encoding: Unspecified
        Extended Identifier: GBIC/SFP defined by twowire interface ID
        Extended RateSelect Compliance: Unspecified
        Identifier: SFP/SFP+/SFP28
        LengthOM3(UnitsOf10m): 0
        Nominal Bit Rate(100Mbs): 103
        Specification compliance:
                SFP+CableTechnology: Passive Cable
        Vendor Date Code(YYYY-MM-DD Lot): 2016-12-21
        Vendor Name: Edgecore
        Vendor OUI: 70-72-cf
        Vendor PN: ET5402-DAC-3M
        Vendor Rev: 01
        Vendor SN: J11852000097
--More--

Ethernet24: SFP EEPROM Not detected

Ethernet25: SFP EEPROM Not detected

Ethernet26: SFP EEPROM Not detected

Ethernet27: SFP EEPROM Not detected

Ethernet28: SFP EEPROM Not detected

Ethernet29: SFP EEPROM Not detected

Ethernet30: SFP EEPROM Not detected

Ethernet31: SFP EEPROM Not detected

Ethernet32: SFP EEPROM Not detected

Ethernet33: SFP EEPROM Not detected

Ethernet34: SFP EEPROM Not detected

Ethernet35: SFP EEPROM Not detected
--More--

Ethernet52: SFP EEPROM Not detected

Ethernet56: SFP EEPROM detected
        Application Advertisement: N/A
        Connector: No separable connector
        DOM Capability:
                Rx_power_support: no
                Temp_support: no
                Tx_power_support: no
                Voltage_support: no
        Encoding: Unspecified
        Extended Identifier: Power Class 1(1.5W max)
        Extended RateSelect Compliance: QSFP+ Rate Select Version 1
        Identifier: QSFP28 or later
        Length Cable Assembly(m): 1
        Nominal Bit Rate(100Mbs): 255
        Specification compliance:
        Vendor Date Code(YYYY-MM-DD Lot): 2017-06-28
        Vendor Name: Edgecore
        Vendor OUI: 70-72-cf
        Vendor PN: ET7402-100DAC-1M
        Vendor Rev: 01
        Vendor SN: J11917004024

Ethernet60: SFP EEPROM Not detected

Ethernet64: SFP EEPROM Not detected

Ethernet68: SFP EEPROM Not detected

Ethernet72: SFP EEPROM Not detected

Ethernet76: SFP EEPROM Not detected
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

### show
admin@sonic:~$ **show**
```
admin@sonic:~$ show
Usage: show [OPTIONS] COMMAND [ARGS]...

  SONiC command line - 'show' command

Options:
  -h, -?, --help  Show this message and exit.

Commands:
  aaa                   Show AAA configuration
  acl                   Show ACL related information
  arp                   Show IP ARP table
  boot                  Show boot configuration
  buffer                Show buffer information
  buffer_pool           Show details of the buffer pools
  chassis-modules       Show chassis-modules information
  clock                 Show date and time
  dropcounters          Show drop counter related information
  ecn                   Show ECN configuration
  environment           Show environmentals (voltages, fans, temps)
  feature               Show feature status
  fgnhg                 Show FGNHG information
  headroom-pool         Show details of headroom pool
  interfaces            Show details of the network interfaces
  ip                    Show IP (IPv4) commands
  ipv6                  Show IPv6 commands
  kdump                 Show kdump configuration, status and information
  kubernetes
  ldap                  Show LDAP configuration
  line                  Show all console lines and their info include...
  lldp                  LLDP (Link Layer Discovery Protocol) information
  logging               Show system log
  mac                   Show MAC (FDB) entries
  management_interface  Show management interface parameters
  mclag                 Show MCLAG related information
  mgmt-vrf              Show management VRF attributes
  mirror_session        Show existing everflow sessions
  mmu                   Show mmu configuration
  muxcable              SONiC command line - 'show muxcable' command
  nat                   Show details of the nat
  ndp                   Show IPv6 Neighbour table
  neigh-suppress        show neigh-suppress
  ntp                   Show NTP information
  pfc                   Show details of the priority-flow-control (pfc)
  pfcwd                 Show details of the pfc watchdog
  pim                   Show details of the pims
  platform              Show platform-specific hardware info
  policer               Show existing policers
  priority-group        Show details of the PGs
  processes             Display process information
  qos                   Show qos related information
  queue                 Show details of the queues
  reboot-cause          Show cause of most recent reboot
  route-map             show route-map
  runningconfiguration  Show current running configuration information
  sag                   show sag information
  services              Show all daemon services
  sflow                 Show sFlow related information
  snmpagentaddress      Show SNMP agent listening IP address configuration
  snmptrap              Show SNMP agent Trap server configuration
  spanning-tree         Show spanning_tree commands
  startupconfiguration  Show startup configuration information
  storm-control         show storm-control
  subinterfaces         Show details of the sub port interfaces
  system                Show system status
  system-health         SONiC command line - 'show system-health' command
  system-memory         Show memory information
  tacacs                Show TACACS+ configuration
  techsupport           Gather information for troubleshooting
  uptime                Show system uptime
  users                 Show users
  version               Show version information
  vlan                  Show VLAN information
  vlan-stacking
  vnet                  Show vnet related information
  vrf                   Show vrf config
  vxlan                 Show vxlan related information
  warm_restart          Show warm restart configuration and state
  watermark             Show details of watermark
  ztp                   Show Zero Touch Provisioning status
admin@sonic:~$
```
