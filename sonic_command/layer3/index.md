[上一頁](https://jian-hong-wu.github.io/blog/sonic_command/)

# Layer 3 commands
* [$ show interfaces counters](https://jian-hong-wu.github.io/blog/sonic_command/layer3/#-show-interfaces-counters)
* [$ show ip route](https://jian-hong-wu.github.io/blog/sonic_command/layer3/#-show-ip-route)
* [$ show ip route 10.1.0.1](https://jian-hong-wu.github.io/blog/sonic_command/layer3/#-show-ip-route-10.1.0.1)
* [$ show ip bgp summary](https://jian-hong-wu.github.io/blog/sonic_command/layer3/#-show-ip-bgp-summary)
* [$ show ip bgp neighbors](https://jian-hong-wu.github.io/blog/sonic_command/layer3/#-show-ip-bgp-neighbors)
* [$ show ip bgp neighbors 10.0.0.1](https://jian-hong-wu.github.io/blog/sonic_command/layer3/#-show-ip-bgp-neighbors-10.0.0.1)
* [$ show ipv6 bgp summary](https://jian-hong-wu.github.io/blog/sonic_command/layer3/#-show-ipv6-bgp-summary)

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

$ show ip route 10.1.0.1
---
<pre>admin@sonic:~$ show ip route 10.1.0.1
Routing entry for 10.1.0.1/32
  Known via &quot;connected&quot;, distance 0, metric 0, best
  Last update 19:58:11 ago
  * directly connected, Loopback0


admin@sonic:~$ 
</pre>
---

$ show ip bgp summary
---
<pre>admin@sonic:~$ show ip bgp summary

IPv4 Unicast Summary:
BGP router identifier 10.1.0.1, local AS number 65100 vrf-id 0
BGP table version 1
RIB entries 1, using 192 bytes of memory
Peers 64, using 1396224 KiB of memory
Peer groups 2, using 128 bytes of memory


Neighbhor      V     AS    MsgRcvd    MsgSent    TblVer    InQ    OutQ  Up/Down    State/PfxRcd    NeighborName
-----------  ---  -----  ---------  ---------  --------  -----  ------  ---------  --------------  --------------
10.0.0.1       4  65200          0          0         0      0       0  never      Active          ARISTA01T2
10.0.0.3       4  65200          0          0         0      0       0  never      Active          ARISTA02T2
10.0.0.5       4  65200          0          0         0      0       0  never      Active          ARISTA03T2
10.0.0.7       4  65200          0          0         0      0       0  never      Active          ARISTA04T2
10.0.0.9       4  65200          0          0         0      0       0  never      Active          ARISTA05T2
10.0.0.11      4  65200          0          0         0      0       0  never      Active          ARISTA06T2
10.0.0.13      4  65200          0          0         0      0       0  never      Active          ARISTA07T2
10.0.0.15      4  65200          0          0         0      0       0  never      Active          ARISTA08T2
10.0.0.17      4  65200          0          0         0      0       0  never      Active          ARISTA09T2
10.0.0.19      4  65200          0          0         0      0       0  never      Active          ARISTA10T2
10.0.0.21      4  65200          0          0         0      0       0  never      Active          ARISTA11T2
10.0.0.23      4  65200          0          0         0      0       0  never      Active          ARISTA12T2
10.0.0.25      4  65200          0          0         0      0       0  never      Active          ARISTA13T2
10.0.0.27      4  65200          0          0         0      0       0  never      Active          ARISTA14T2
10.0.0.29      4  65200          0          0         0      0       0  never      Active          ARISTA15T2
10.0.0.31      4  65200          0          0         0      0       0  never      Active          ARISTA16T2
10.0.0.33      4  65200          0          0         0      0       0  never      Active          ARISTA17T2
10.0.0.35      4  65200          0          0         0      0       0  never      Active          ARISTA18T2
10.0.0.37      4  65200          0          0         0      0       0  never      Active          ARISTA19T2
10.0.0.39      4  65200          0          0         0      0       0  never      Active          ARISTA20T2
10.0.0.41      4  65200          0          0         0      0       0  never      Active          ARISTA21T2
10.0.0.43      4  65200          0          0         0      0       0  never      Active          ARISTA22T2
10.0.0.45      4  65200          0          0         0      0       0  never      Active          ARISTA23T2
10.0.0.47      4  65200          0          0         0      0       0  never      Active          ARISTA24T2
10.0.0.49      4  65200          0          0         0      0       0  never      Active          ARISTA25T2
10.0.0.51      4  65200          0          0         0      0       0  never      Active          ARISTA26T2
10.0.0.53      4  65200          0          0         0      0       0  never      Active          ARISTA27T2
10.0.0.55      4  65200          0          0         0      0       0  never      Active          ARISTA28T2
10.0.0.57      4  65200          0          0         0      0       0  never      Active          ARISTA29T2
10.0.0.59      4  65200          0          0         0      0       0  never      Active          ARISTA30T2
10.0.0.61      4  65200          0          0         0      0       0  never      Active          ARISTA31T2
10.0.0.63      4  65200          0          0         0      0       0  never      Active          ARISTA32T2
10.0.0.65      4  64001          0          0         0      0       0  never      Active          ARISTA01T0
10.0.0.67      4  64002          0          0         0      0       0  never      Active          ARISTA02T0
10.0.0.69      4  64003          0          0         0      0       0  never      Active          ARISTA03T0
10.0.0.71      4  64004          0          0         0      0       0  never      Active          ARISTA04T0
10.0.0.73      4  64005          0          0         0      0       0  never      Active          ARISTA05T0
10.0.0.75      4  64006          0          0         0      0       0  never      Active          ARISTA06T0
10.0.0.77      4  64007          0          0         0      0       0  never      Active          ARISTA07T0
10.0.0.79      4  64008          0          0         0      0       0  never      Active          ARISTA08T0
10.0.0.81      4  64009          0          0         0      0       0  never      Active          ARISTA09T0
10.0.0.83      4  64010          0          0         0      0       0  never      Active          ARISTA10T0
10.0.0.85      4  64011          0          0         0      0       0  never      Active          ARISTA11T0
10.0.0.87      4  64012          0          0         0      0       0  never      Active          ARISTA12T0
10.0.0.89      4  64013          0          0         0      0       0  never      Active          ARISTA13T0
10.0.0.91      4  64014          0          0         0      0       0  never      Active          ARISTA14T0
10.0.0.93      4  64015          0          0         0      0       0  never      Active          ARISTA15T0
10.0.0.95      4  64016          0          0         0      0       0  never      Active          ARISTA16T0
10.0.0.97      4  64017          0          0         0      0       0  never      Active          ARISTA17T0
10.0.0.99      4  64018          0          0         0      0       0  never      Active          ARISTA18T0
10.0.0.101     4  64019          0          0         0      0       0  never      Active          ARISTA19T0
10.0.0.103     4  64020          0          0         0      0       0  never      Active          ARISTA20T0
10.0.0.105     4  64021          0          0         0      0       0  never      Active          ARISTA21T0
10.0.0.107     4  64022          0          0         0      0       0  never      Active          ARISTA22T0
10.0.0.109     4  64023          0          0         0      0       0  never      Active          ARISTA23T0
10.0.0.111     4  64024          0          0         0      0       0  never      Active          ARISTA24T0
10.0.0.113     4  64025          0          0         0      0       0  never      Active          ARISTA25T0
10.0.0.115     4  64026          0          0         0      0       0  never      Active          ARISTA26T0
10.0.0.117     4  64027          0          0         0      0       0  never      Active          ARISTA27T0
10.0.0.119     4  64028          0          0         0      0       0  never      Active          ARISTA28T0
10.0.0.121     4  64029          0          0         0      0       0  never      Active          ARISTA29T0
10.0.0.123     4  64030          0          0         0      0       0  never      Active          ARISTA30T0
10.0.0.125     4  64031          0          0         0      0       0  never      Active          ARISTA31T0
10.0.0.127     4  64032          0          0         0      0       0  never      Active          ARISTA32T0

Total number of neighbors 64
admin@sonic:~$ 
</pre>
---
$ show ip bgp neighbors
---
<pre>admin@sonic:~$ show ip bgp neighbors
BGP neighbor is 10.0.0.1, remote AS 65200, local AS 65100, external link
 Description: ARISTA01T2
 Member of peer-group PEER_V4 for session parameters
  BGP version 4, remote router ID 0.0.0.0, local router ID 10.1.0.1
  BGP state = Active
  Last read 20:01:01, Last write never
  Hold time is 180, keepalive interval is 60 seconds
  Graceful restart information:
    Local GR Mode: Restart*
    Remote GR Mode: NotApplicable
    R bit: False
    Timers:
      Configured Restart Time(sec): 240
      Received Restart Time(sec): 0
  Message statistics:
    Inq depth is 0
    Outq depth is 0
                         Sent       Rcvd
    Opens:                  0          0
    Notifications:          0          0
    Updates:                0          0
    Keepalives:             0          0
    Route Refresh:          0          0
    Capability:             0          0
    Total:                  0          0
  Minimum time between advertisement runs is 0 seconds

 For address family: IPv4 Unicast
  PEER_V4 peer-group member
  Not part of any update group
  Inbound soft reconfiguration allowed
  Community attribute sent to this neighbor(all)
  Inbound path policy configured
  Outbound path policy configured
  Route map for incoming advertisements is *FROM_BGP_PEER_V4
  Route map for outgoing advertisements is *TO_BGP_PEER_V4
  0 accepted prefixes

  Connections established 0; dropped 0
  Last reset 20:01:01,  Waiting for NHT
BGP Connect Retry Timer in Seconds: 120
Next connect timer due in 63 seconds
Read thread: off  Write thread: off  FD used: -1

BGP neighbor is 10.0.0.3, remote AS 65200, local AS 65100, external link
 Description: ARISTA02T2
 Member of peer-group PEER_V4 for session parameters
  BGP version 4, remote router ID 0.0.0.0, local router ID 10.1.0.1
  BGP state = Active
  Last read 20:01:02, Last write never
  Hold time is 180, keepalive interval is 60 seconds
  Graceful restart information:
    Local GR Mode: Restart*
    Remote GR Mode: NotApplicable
    R bit: False
    Timers:
      Configured Restart Time(sec): 240
      Received Restart Time(sec): 0
  Message statistics:
    Inq depth is 0
    Outq depth is 0
                         Sent       Rcvd
    Opens:                  0          0
    Notifications:          0          0
    Updates:                0          0
    Keepalives:             0          0
    Route Refresh:          0          0
    Capability:             0          0
    Total:                  0          0
  Minimum time between advertisement runs is 0 seconds

 For address family: IPv4 Unicast
  PEER_V4 peer-group member
  Not part of any update group
  Inbound soft reconfiguration allowed
  Community attribute sent to this neighbor(all)
  Inbound path policy configured
  Outbound path policy configured
  Route map for incoming advertisements is *FROM_BGP_PEER_V4
  Route map for outgoing advertisements is *TO_BGP_PEER_V4
  0 accepted prefixes

  Connections established 0; dropped 0
  Last reset 20:01:02,  Waiting for NHT
BGP Connect Retry Timer in Seconds: 120
Next connect timer due in 63 seconds
Read thread: off  Write thread: off  FD used: -1


admin@sonic:~$ 
</pre>
---

$ show ip bgp neighbors 10.0.0.1
---
<pre>admin@sonic:~$ show ip bgp neighbors 10.0.0.1
BGP neighbor is 10.0.0.1, remote AS 65200, local AS 65100, external link
 Description: ARISTA01T2
 Member of peer-group PEER_V4 for session parameters
  BGP version 4, remote router ID 0.0.0.0, local router ID 10.1.0.1
  BGP state = Active
  Last read 20:05:48, Last write never
  Hold time is 180, keepalive interval is 60 seconds
  Graceful restart information:
    Local GR Mode: Restart*
    Remote GR Mode: NotApplicable
    R bit: False
    Timers:
      Configured Restart Time(sec): 240
      Received Restart Time(sec): 0
  Message statistics:
    Inq depth is 0
    Outq depth is 0
                         Sent       Rcvd
    Opens:                  0          0
    Notifications:          0          0
    Updates:                0          0
    Keepalives:             0          0
    Route Refresh:          0          0
    Capability:             0          0
    Total:                  0          0
  Minimum time between advertisement runs is 0 seconds

 For address family: IPv4 Unicast
  PEER_V4 peer-group member
  Not part of any update group
  Inbound soft reconfiguration allowed
  Community attribute sent to this neighbor(all)
  Inbound path policy configured
  Outbound path policy configured
  Route map for incoming advertisements is *FROM_BGP_PEER_V4
  Route map for outgoing advertisements is *TO_BGP_PEER_V4
  0 accepted prefixes

  Connections established 0; dropped 0
  Last reset 20:05:48,  Waiting for NHT
BGP Connect Retry Timer in Seconds: 120
Next connect timer due in 16 seconds
Read thread: off  Write thread: off  FD used: -1


admin@sonic:~$ 

</pre>
---

$ show ipv6 bgp summary
---
<pre>admin@sonic:~$ show ipv6 bgp summary
Usage: show ipv6 bgp summary [OPTIONS]
Try &quot;show ipv6 bgp summary -h&quot; for help.

Error: bgp summary from bgp container in invalid format
admin@sonic:~$ 
</pre>
---
