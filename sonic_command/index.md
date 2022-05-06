[上一頁](https://jian-hong-wu.github.io/blog/)

# Sonic Commands

[General commands](https://jian-hong-wu.github.io/blog/sonic_command/general/)  
[Layer 2 commands](https://jian-hong-wu.github.io/blog/sonic_command/layer2/)  
[Layer 3 commands](https://jian-hong-wu.github.io/blog/sonic_command/layer3/)  

[bcmcmd](https://jian-hong-wu.github.io/blog/sonic_commands/bcmcmd/)  

[show](/blog/sonic_commands/show/)    // show command  
[ip](/blog/sonic_commands/ip/)    // ip command  

## show ip route
[ip route show](/blog/sonic_commands/ip/)    // show ip route  
[ip -s link](/blog/sonic_commands/ip/)    // show port statistics  
[ip -s link ls Ethernet1](/blog/sonic_commands/ip/)    // show port statistics  

[ip addr add 192.168.0.24/24 dev Ethernet2](/blog/sonic_commands/ip/)    // set ip address  
[ip addr show dev Ethernet2](/blog/sonic_commands/ip/)    // show ip address  

## system status
[show logging | more](/blog/sonic_commands/logging/)    //show system log  
[psuutil status](/blog/sonic_commands/)    //show psu status  
[sfputil show eeprom](/blog/sonic_commands/)    // show transceiver eeprom  
[sfputil show presence](/blog/sonic_commands/)    // show transceiver present  
[sfputil show presence --port Ethernet0](/blog/sonic_commands/)    // show transceiver present  

## enable lpmode
[sfputil lpmode on Ethernet1](/blog/sonic_commands/)    // enable lpmode  

## show/clear mac table
[fdbshow](/blog/sonic_commands/)    // show mac table  
[show mac](/blog/sonic_commands/)    // show mac table  
[sonic-clear fdb all](/blog/sonic_commands/)    // clear mac table  

## How to create LAG portchannel using minigraph.xml file
[vi /etc/sonic/minigraph.xml](/blog/sonic_commands/)    // create LAG portchannel  
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
[show interfaces portchannel](/blog/sonic_commands/)  // show interfaces portchannel  

## teamshow


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

