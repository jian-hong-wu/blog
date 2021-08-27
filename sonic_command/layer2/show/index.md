[上一頁](/blog/sonic_command/layer2/)

### Show commands

$ show
---
<pre>admin@sonic:~$ show
Usage: show [OPTIONS] COMMAND [ARGS]...

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
$ show environment
---
<pre>admin@sonic:~$ show environment
Error response from daemon: Container 75078ce1ed609c70e6992927281373135268d09dead3ce932b3dfad464f4ceb0 is not running
admin@sonic:~$ </pre>
---
$ show platform ?
---
<pre>admin@sonic:~$ show platform ?
Usage: show platform [OPTIONS] COMMAND [ARGS]...

  Show platform-specific hardware info

Options:
  -h, -?, --help  Show this message and exit.

Commands:
  fan          Show fan status information
  firmware     Show firmware information
  pcieinfo     Show Device PCIe Info
  psustatus    Show PSU status information
  ssdhealth    Show SSD Health information
  summary      Show hardware platform information
  syseeprom    Show system EEPROM information
  temperature  Show device temperature information
admin@sonic:~$ </pre>
---
$ show platform firmware
---
<pre>admin@sonic:~$ show platform firmware
Traceback (most recent call last):
  File &quot;/usr/local/lib/python3.7/dist-packages/fwutil/__init__.py&quot;, line 2, in &lt;module&gt;
    from sonic_platform.platform import Platform
ModuleNotFoundError: No module named &apos;sonic_platform&apos;

During handling of the above exception, another exception occurred:

Traceback (most recent call last):
  File &quot;/usr/local/bin/fwutil&quot;, line 5, in &lt;module&gt;
    from fwutil.main import cli
  File &quot;/usr/local/lib/python3.7/dist-packages/fwutil/__init__.py&quot;, line 5, in &lt;module&gt;
    raise ImportError(&quot;Required module not found: {}&quot;.format(str(e)))
ImportError: Required module not found: No module named &apos;sonic_platform&apos;
admin@sonic:~$ </pre>
---

$ show ip

$ show interface

$ show vlan

$ show vxlan

$ show watermark

$ show ztp


$ show environment

![](https://jian-hong-wu.github.io/blog/sonic_command/general/1.png)

$ show platform summary

![](https://jian-hong-wu.github.io/blog/sonic_command/general/2.png)

$ show platform syseeprom

![](https://jian-hong-wu.github.io/blog/sonic_command/general/3.png)

$ show interface alias

![](https://jian-hong-wu.github.io/blog/sonic_command/general/7.png)

$ show interface breakout

![](https://jian-hong-wu.github.io/blog/sonic_command/general/8.png)

$ show interface description

![](https://jian-hong-wu.github.io/blog/sonic_command/general/10.png)

$ show interface naming_mode

![](https://jian-hong-wu.github.io/blog/sonic_command/general/11.png)

$ show interface neighbor expected

![](https://jian-hong-wu.github.io/blog/sonic_command/general/12.png)

$ show interface status

![](https://jian-hong-wu.github.io/blog/sonic_command/general/14.png)

$ show interfaces transceiver eeprom --dom Ethernet0

![](https://jian-hong-wu.github.io/blog/sonic_command/general/4.png)

$ show interfaces transceiver lpmode Ethernet100

![](https://jian-hong-wu.github.io/blog/sonic_command/general/5.png)

$ show interfaces transceiver presence Ethernet100

![](https://jian-hong-wu.github.io/blog/sonic_command/general/6.png)

