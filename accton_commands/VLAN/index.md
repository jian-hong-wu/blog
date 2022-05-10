# VLAN Commands

## Create VLAN1 and VLAN2 on the switch
```
admin@sonic:~$ sudo config vlan add 1       
admin@sonic:~$ sudo config vlan add 2
```

Make sure that the port configuration of the VLAN member is not a router port, if you receive the following error:
```
admin@sonic:~$ sudo config vlan member add 1 Ethernet48
Usage: config vlan member add [OPTIONS]  
Try "config vlan member add -h" for help.

Error: Ethernet48 is a L3 interface!
```

## Set Etherenet48 as VLAN1 untag member
```
admin@sonic:~$ sudo config vlan member add -u 1 Ethernet48
```

## Set Ethernet52 as VLAN2 tag member.
```
admin@sonic:~$ sudo config vlan member add 2 Ethernet52
```




refer to htttps://support.edge-core.com/hc/en-us/articles/900000210426--Edgecore-SONiC-VLAN-Inter-VLAN-Routing
