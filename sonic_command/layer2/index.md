[上一頁](/blog/sonic_command/)

### Layer 2 commands
* [$ show (各种各样的命令)](/blog/sonic_command/layer2/show/)
* [$ show platform & environment](/blog/sonic_command/layer2/show/platform/)
* [$ show ip](/blog/sonic_command/layer2/show/ip/)
* [$ show interface](/blog/sonic_command/layer2/show/interface/)
* [$ show vlan & vxlan](/blog/sonic_command/layer2/show/vlan/)
* [$ show (其他指令)](/blog/sonic_command/layer2/show/misc/)

Show是最常用的指令

$ show
---
<pre>admin@sonic:~$ show
Usage: show [OPTIONS] COMMAND [ARGS]...
命令
  SONiC command line - &apos;show&apos; command

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
  line                  Show all console lines and their info include...
  lldp                  LLDP (Link Layer Discovery Protocol) information
  logging               Show system log
  mac                   Show MAC (FDB) entries
  management_interface  Show management interface parameters
  mgmt-vrf              Show management VRF attributes
  mirror_session        Show existing everflow sessions
  mmu                   Show mmu configuration
  muxcable              SONiC command line - &apos;show muxcable&apos; command
  nat                   Show details of the nat
  ndp                   Show IPv6 Neighbour table
  ntp                   Show NTP information
  pfc                   Show details of the priority-flow-control (pfc)
  pfcwd                 Show details of the pfc watchdog
  platform              Show platform-specific hardware info
  policer               Show existing policers
  priority-group        Show details of the PGs
  processes             Display process information
  queue                 Show details of the queues
  reboot-cause          Show cause of most recent reboot
  route-map             show route-map
  runningconfiguration  Show current running configuration information
  services              Show all daemon services
  sflow                 Show sFlow related information
  snmpagentaddress      Show SNMP agent listening IP address configuration
  snmptrap              Show SNMP agent Trap server configuration
  startupconfiguration  Show startup configuration information
  subinterfaces         Show details of the sub port interfaces
  system-health         SONiC command line - &apos;show system-health&apos; command
  system-memory         Show memory information
  tacacs                Show TACACS+ configuration
  techsupport           Gather information for troubleshooting
  uptime                Show system uptime
  users                 Show users
  version               Show version information
  vlan                  Show VLAN information
  vnet                  Show vnet related information
  vrf                   Show vrf config
  vxlan                 Show vxlan related information
  warm_restart          Show warm restart configuration and state
  watermark             Show details of watermark
  ztp                   Show Zero Touch Provisioning status
admin@sonic:~$</pre>
---


