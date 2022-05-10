# Transceiver Commands  

## relative commands  
1. Switch Port Attributes  
2. LAG (Link Aggregation)  
3. Transceiver status and DDMI  
4. MTU (Maximum Transmission Unit)  
5. Counter (Port counter and L3 RIF counter)  
6. Dynamic Port Breakout)  


## Check transceiver present
```
admin@sonic:~$ show interfaces transceiver presence
Port        Presence
----------  -----------
Ethernet0   Not present
…
Omitted
…
Ethernet47  Not present
Ethernet48  Present
Ethernet52  Present
Ethernet56  Present
Ethernet60  Present
Ethernet64  Not present
Ethernet68  Not present
```

## default LPmode is high-power mode




Reference web page:
https://support.edge-core.com/hc/en-us/articles/900000208666--Edgecore-SONiC-Transceiver-status-and-DDMI

