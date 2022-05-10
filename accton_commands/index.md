[上一頁](https://jian-hong-wu.github.io/blog/)

# Accton Commands

[Utility commands](/blog/accton_command/general/)  
[Switching commands](/blog/accton_command/layer2/)  
[Routing commands](/blog/accton_command/layer3/)  

[bcmcmd](/blog/accton_commands/bcmcmd/)  

[show](/blog/accton_commands/show/)    // show command  
[ip](/blog/accton_commands/ip/)    // ip command  

## show ip route
[ip route show](/blog/accton_commands/ip/)    // show ip route  
[ip -s link](/blog/accton_commands/ip/)    // show port statistics  
[ip -s link ls Ethernet1](/blog/accton_commands/ip/)    // show port statistics  

[ip addr add 192.168.0.24/24 dev Ethernet2](/blog/accton_commands/ip/)    // set ip address  
[ip addr show dev Ethernet2](/blog/accton_commands/ip/)    // show ip address  

## system status
[show logging](/blog/accton_commands/show/)    //show system log  
[show logging | more](/blog/accton_commands/show/)    //show system log
[psuutil](/blog/accton_commands/psuutil)    //psuutil command
[sudo psuutil status](/blog/accton_commands/)    //show psu status  
[sfputil](/blog/accton_commands/sfputil)    //sfputil command
[sudo sfputil show eeprom](/blog/accton_commands/)    // show transceiver eeprom  
[shdo sfputil show presence](/blog/accton_commands/)    // show transceiver present  
[sfputil show presence --port Ethernet0](/blog/accton_commands/)    // show transceiver present  

## enable lpmode/reset SFP transceiver/show version
[sudo sfputil lpmode on Ethernet1](/blog/accton_commands/)    // enable lpmode  
[sudo sfputil reset Ethernet1](/blog/accton_commands/)    // enable lpmode  
[sudo sfputil version](/blog/accton_commands/)    // enable lpmode  

## show/clear mac table
[fdbshow](/blog/accton_commands/)    // show mac table  
[show mac](/blog/accton_commands/)    // show mac table  
[sonic-clear fdb all](/blog/accton_commands/)    // clear mac table  

## How to create LAG portchannel using minigraph.xml file
[vi /etc/sonic/minigraph.xml](/blog/accton_commands/)    // create LAG portchannel  
```
<PortChannelInterfaces>
<PortChannel>
<Name>PortChannel01</Name>
<AttachTo>Ethernet112,Ethernet126</AttachTo>
<SubInterface/>
</PortChannel>
<PortChannel>
<Name>PortChannel03</Name>
<AttachTo>Ethernet116</AttachTo>
<SubInterface/>
</PortChannel>
</PortChannelInterfaces>
```
[config save]    // save configuration  

## show interfaces portchannel
[show interfaces portchannel](/blog/accton_commands/)  // show interfaces portchannel  

## teamshow
```
[teamshow]
Flags: A - active, I - inactive, Up - up, Dw - Down, N/A - not available, S - selected, D - deselected
No. Team Dev Protocol Ports
----- ------------- ----------- -------
01 PortChannel01 LACP(A)(Dw) N/A
03 PortChannel03 LACP(A)(Dw) N/A
```

## configuration using .json file
1. Create a myconfig.json file
2. edit myconfig.json file
3. config load myconfig.json
4. config file example

```
{
    "VLAN": {
        "vlan100": {
        "vlanid": 100
        },
        "vlan200": {
        "vlanid": 200
        }
    },
    "VLAN_MEMBER": {
        "vlan100|Ethernet1": {
        "tagging_mode": "untagged"
        },
        "vlan200|Ethernet2": {
        "tagging_mode": "tagged"
        }
    }
}
```

## Configure 10G interface to be 1G interface
[Configure 10G interface to be 1G interface](/blog/accton_commands/config/)    // configuration

## Configure 25G interface to be 10G interface
```
admin@sonic:~$ sudo config interface speed Ethernet0 10000
```

If it is in breakout mode,
```
admin@sonic:~$ sudo config interface speed Ethernet0 10000
Can't set the port speed.
```

```
admin@sonic:~$ show interfaces status
  Interface            Lanes    Speed    MTU    FEC    Alias    Vlan    Oper    Admin             Type    Asym PFC
-----------  ---------------  -------  -----  -----  -------  ------  ------  -------  ---------------  ----------
  Ethernet0                3      25G   9100   none   Eth5/3  routed    down       up   SFP/SFP+/SFP28         N/A
  Ethernet1                2      25G   9100   none   Eth5/2  routed    down       up              N/A         N/A
  Ethernet2                4      25G   9100   none   Eth5/4  routed    down       up              N/A         N/A
  Ethernet3                8      25G   9100   none   Eth6/4  routed    down       up   SFP/SFP+/SFP28         N/A
  Ethernet4                7      25G   9100   none   Eth6/3  routed    down       up              N/A         N/A
  Ethernet5                1      25G   9100   none   Eth5/1  routed    down       up              N/A         N/A
```
(Note: how to set color in the code block?)

Check the breakout option availability and current breakout mode.
```
admin@sonic:~$ show interfaces breakout
{
    "Ethernet5": {
        "child port speeds": "25G,25G,25G,25G",
        "index": "6,2,1,3",
        "lanes": "1,2,3,4",
        "child ports": "Ethernet0,Ethernet1,Ethernet2,Ethernet5",
        "Current Breakout Mode": "4x25G",
        "interface_ids": "5,1,0,2",
        "default_brkout_mode": "4x25G",
        "breakout_modes": "4x25G,4x10G",
        "alias_at_lanes": "Eth5/1,Eth5/2,Eth5/3,Eth5/4"
...
omitted
```

Configure the port group "Ethernet5" to 10G
```
admin@sonic:~$ sudo config interface breakout Ethernet5 '4x10G'
Do you want to Breakout the port, continue? [y/N]: y

Running Breakout Mode : 4x25G
Target Breakout Mode : 4x10G
...
omitted
```

Check the status
```
admin@sonic:~$ show interfaces status
  Interface            Lanes    Speed    MTU    FEC    Alias    Vlan    Oper    Admin             Type    Asym PFC
-----------  ---------------  -------  -----  -----  -------  ------  ------  -------  ---------------  ----------
  Ethernet0                3      10G   9100   none   Eth5/3  routed    down     down   SFP/SFP+/SFP28         N/A
  Ethernet1                2      10G   9100   none   Eth5/2  routed    down     down              N/A         N/A
  Ethernet2                4      10G   9100   none   Eth5/4  routed    down     down              N/A         N/A
  Ethernet3                8      25G   9100   none   Eth6/4  routed    down       up   SFP/SFP+/SFP28         N/A
  Ethernet4                7      25G   9100   none   Eth6/3  routed    down       up              N/A         N/A
  Ethernet5                1      10G   9100   none   Eth5/1  routed    down     down              N/A         N/A
```

## Configure 100G interface (QSFP+) to be 40G interface
```
admin@sonic:~$ sudo config interface speed Ethernet48 40000
admin@sonic:~$ sudo config interface speed Ethernet52 40000
```
Check the interface speed
```
admin@sonic:~$ show interface status | grep 'Ethernet48\|Ethernet52'
 Ethernet48  37,38,39,40      40G   9100    N/A  Eth49/1  routed    down       up  QSFP+ or later         N/A
 Ethernet52  29,30,31,32      40G   9100    N/A  Eth50/1  routed    down       up  QSFP+ or later         N/A
```

## Configure FEC (Forward Error Correction) to RS mode
Step 1:  Configure FEC to RS mode.
```
admin@sonic:~$ sudo config interface fec Ethernet0 rs
```
Step 2: Checking the FEC status.
```
admin@sonic:~$ show interfaces status
  Interface            Lanes    Speed    MTU    FEC    Alias    Vlan    Oper    Admin             Type    Asym PFC
-----------  ---------------  -------  -----  -----  -------  ------  ------  -------  ---------------  ----------
  Ethernet0          1,2,3,4     100G   9100     rs   Eth1/1  routed    down       up              N/A         N/A
  Ethernet4          5,6,7,8     100G   9100   none   Eth2/1  routed    down       up              N/A         N/A
  Ethernet8       9,10,11,12     100G   9100   none   Eth3/1  routed    down       up              N/A         N/A
 Ethernet12      13,14,15,16     100G   9100   none   Eth4/1  routed    down       up              N/A         N/A
```


## Configure the Etherner0 to auto-negotiation
Step 1: Enable the auto-negotiation on Ethernet0
```
admin@sonic:~$ sudo config interface autoneg Ethernet0 enabled
```
Step 2: Check configuration status
```
admin@sonic:~$ show interface autoneg status Ethernet0
  Interface    Auto-Neg Mode    Oper Speed    Adv Speeds    Oper    Admin
-----------  ---------------  ------------  ------------  ------  -------
  Ethernet0          enabled           10G           N/A    down       up
```
Step 3: verify configuration
```
admin@sonic:~$ sudo vi /etc/sonic/config_db.json
{
... omitted

        "Ethernet0": {
            "admin_status": "up",
            "alias": "Eth5/3",
            "index": "1",
            "lanes": "3",
            "mtu": "9100",
            "autoneg": "1",
            "parent_port": "Ethernet5",
            "speed": "25000"
        },

... omitted
}
admin@sonic:~$ sudo config reload -y
```



