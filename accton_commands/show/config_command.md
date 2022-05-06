# config command

### sudo config interface fec Eternet0 rs



### sudo config interface 
admin@sonic:~$ **sudo config interface**
```
admin@sonic:~$ sudo config interface
Usage: config interface [OPTIONS] COMMAND [ARGS]...

  Interface-related configuration tasks

Options:
  -n, --namespace []  Namespace name
  -?, -h, --help      Show this message and exit.

Commands:
  advertised-speeds  Set interface advertised speeds
  autoneg            Set interface auto negotiation mode
  breakout           Set interface breakout mode
  buffer             Set or clear buffer configuration
  cable-length       Set lossless PGs for the interface
  description        Set interface description
  fec                Set interface fec
  ip                 Add or remove IP address
  mtu                Set interface mtu
  pfc                Set PFC configuration.
  rate-limit         Rate limit configuration.
  sag
  shutdown           Shut down interface
  speed              Set interface speed
  startup            Start up interface
  storm-control      Configure storm-control
  transceiver        SFP transceiver configuration
  vrf                Bind or unbind VRF
admin@sonic:~$
```

### sudo config
admin@sonic:~$ **sudo config**
```
admin@sonic:~$ sudo config
Usage: config [OPTIONS] COMMAND [ARGS]...

  SONiC command line - 'config' command

Options:
  -?, -h, --help  Show this message and exit.

Commands:
  aaa                    AAA command line
  acl                    ACL-related configuration tasks
  bgp                    BGP-related configuration tasks
  buffer                 Configure buffer_profile
  chassis-modules        Configure chassis-modules options
  console                Console-related configuration tasks
  dropcounters           Drop counter related configuration tasks
  ecn                    ECN-related configuration tasks
  feature                Configure features
  hostname               Change device hostname without impacting the...
  interface              Interface-related configuration tasks
  interface_naming_mode  Modify interface naming mode for interacting with...
  kdump                  Configure kdump
  kubernetes             kubernetes command line
  ldap                   LDAP server configuration
  lldp                   LLDP daemon related configuration
  load                   Import a previous saved config DB dump file.
  load_mgmt_config       Reconfigure hostname and mgmt interface based on...
  load_minigraph         Reconfigure based on minigraph.
  loopback               Loopback-related configuration tasks
  mclag                  Multi-Chassis Link Aggregation Group-related...
  mirror_session
  muxcable               SONiC command line - 'show muxcable' command
  nat                    NAT-related configuration tasks
  neigh-suppress         Neighbour Suppress VLAN-related configuration
  ntp                    NTP server configuration tasks
  pfcwd                  Configure pfc watchdog
  platform               Platform-related configuration tasks
  policer                Policer configuration tasks
  portchannel
  qos                    QoS-related configuration tasks
  reload                 Clear current configuration and import a previous...
  route                  route-related configuration tasks
  sag                    Static Anycast Gateway
  save                   Export current config DB to a file on disk.
  sflow                  sFlow-related configuration tasks
  snmpagentaddress       SNMP agent listening IP address, port, vrf...
  snmptrap               SNMP Trap server configuration to send traps
  spanning-tree          STP command line
  synchronous_mode       Enable or disable synchronous mode between...
  syslog                 Syslog server configuration tasks
  tacacs                 TACACS+ server configuration
  vlan                   VLAN-related configuration tasks
  vlan-stacking
  vrf                    VRF-related configuration tasks
  vxlan
  warm_restart           warm_restart-related configuration tasks
  watermark              Configure watermark
  ztp                    Configure Zero Touch Provisioning
admin@sonic:~
```
