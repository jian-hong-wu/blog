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


## Configure 25G interface to be 10G interface
[Configure 25G interface to be 10G interface](/blog/accton_commands/config/)    // configuration

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


