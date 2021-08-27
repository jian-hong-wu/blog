[上一頁](https://jian-hong-wu.github.io/blog/sonic_command/)

# Layer 3 commands

$ show interfaces counters
---
<pre>admin@sonic:~$ show interfaces counters
      IFACE    STATE    RX_OK    RX_BPS    RX_UTIL    RX_ERR    RX_DRP    RX_OVR    TX_OK    TX_BPS    TX_UTIL    TX_ERR    TX_DRP    TX_OVR
-----------  -------  -------  --------  ---------  --------  --------  --------  -------  --------  ---------  --------  --------  --------
  Ethernet0        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
  Ethernet4        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
  Ethernet8        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet12        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet16        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet20        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet24        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet28        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet32        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet36        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet40        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet44        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet48        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet52        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet56        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet60        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet64        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet68        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet72        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet76        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet80        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet84        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet88        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet92        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
 Ethernet96        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet100        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet104        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet108        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet112        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet116        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet120        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet124        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet128        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet132        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet136        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet140        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet144        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet148        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet152        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet156        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet160        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet164        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet168        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet172        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet176        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet180        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet184        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet188        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet192        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet196        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet200        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet204        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet208        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet212        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet216        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet220        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet224        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet228        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet232        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet236        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet240        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet244        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet248        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
Ethernet252        D        0       N/A        N/A         0         0         0        0       N/A        N/A         0         0         0
admin@sonic:~$ 
</pre>
---

$ show ip route
---
<pre>admin@sonic:~$ show ip route
Codes: K - kernel route, C - connected, S - static, R - RIP,
       O - OSPF, I - IS-IS, B - BGP, E - EIGRP, N - NHRP,
       T - Table, v - VNC, V - VNC-Direct, A - Babel, D - SHARP,
       F - PBR, f - OpenFabric,
       &gt; - selected route, * - FIB route, q - queued, r - rejected, b - backup

C&gt;* 10.1.0.1/32 is directly connected, Loopback0, 19:54:12

admin@sonic:~$ 
</pre>
---
![](https://jian-hong-wu.github.io/blog/sonic_command/layer3/2.png)

$ show ip route 10.0.0.12

![](https://jian-hong-wu.github.io/blog/sonic_command/layer3/3.png)

$ show ip bgp summary

![](https://jian-hong-wu.github.io/blog/sonic_command/layer3/11.png)

$ show ip bgp neighbors

![](https://jian-hong-wu.github.io/blog/sonic_command/layer3/12.png)

$ show ip bgp neighbors 10.0.0.57

![](https://jian-hong-wu.github.io/blog/sonic_command/layer3/13.png)

$ show ipv6 bgp summary

![](https://jian-hong-wu.github.io/blog/sonic_command/layer3/14.png)
