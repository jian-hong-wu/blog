# show version command

### show version -h
admin@sonic:~$ **show version -h**
```
admin@sonic:~$ show version -h
Usage: show version [OPTIONS]

  Show version information

Options:
  --verbose       Enable verbose output
  -h, -?, --help  Show this message and exit.
admin@sonic:~$
```

### show version
admin@sonic:~$ **show version**
```
admin@sonic:~$ show version

SONiC Software Version: SONiC.Edgecore-SONiC_20220420_052156_ec202012_323
Distribution: Debian 10.12
Kernel: 4.19.0-12-2-amd64
Build commit: 284eb07f1
Build date: Wed Apr 20 05:49:35 UTC 2022
Built by: ubuntu@ip-10-5-1-225

Platform: x86_64-accton_as7326_56x-r0
HwSKU: Accton-AS7326-56X
ASIC: broadcom
ASIC Count: 1
Serial Number: 732656X1951017
Uptime: 11:33:17 up 8 days,  1:21,  1 user,  load average: 2.06, 1.11, 1.07

Docker images:
REPOSITORY                    TAG                                           IMAGE ID            SIZE
docker-fpm-frr                Edgecore-SONiC_20220420_052156_ec202012_323   35f84451ecc5        520MB
docker-fpm-frr                latest                                        35f84451ecc5        520MB
docker-teamd                  Edgecore-SONiC_20220420_052156_ec202012_323   f2bd286a967f        491MB
docker-teamd                  latest                                        f2bd286a967f        491MB
docker-orchagent              Edgecore-SONiC_20220420_052156_ec202012_323   bfd076b647e0        527MB
docker-orchagent              latest                                        bfd076b647e0        527MB
docker-nat                    Edgecore-SONiC_20220420_052156_ec202012_323   3c67caec480d        494MB
docker-nat                    latest                                        3c67caec480d        494MB
docker-iccpd                  Edgecore-SONiC_20220420_052156_ec202012_323   fb461ab08a89        492MB
docker-iccpd                  latest                                        fb461ab08a89        492MB
docker-sflow                  Edgecore-SONiC_20220420_052156_ec202012_323   6b1202d40cba        492MB
docker-sflow                  latest                                        6b1202d40cba        492MB
docker-stp                    Edgecore-SONiC_20220420_052156_ec202012_323   1b818a76f760        426MB
docker-stp                    latest                                        1b818a76f760        426MB
docker-syncd-brcm             Edgecore-SONiC_20220420_052156_ec202012_323   8c913d1fdb87        695MB
docker-syncd-brcm             latest                                        8c913d1fdb87        695MB
docker-dhcp-relay             Edgecore-SONiC_20220420_052156_ec202012_323   a12585e3e5f9        486MB
docker-dhcp-relay             latest                                        a12585e3e5f9        486MB
docker-platform-monitor       Edgecore-SONiC_20220420_052156_ec202012_323   f56dee9aeadc        624MB
docker-platform-monitor       latest                                        f56dee9aeadc        624MB
docker-database               Edgecore-SONiC_20220420_052156_ec202012_323   19a30710d923        416MB
docker-database               latest                                        19a30710d923        416MB
docker-lldp                   Edgecore-SONiC_20220420_052156_ec202012_323   fcff49714eb9        450MB
docker-lldp                   latest                                        fcff49714eb9        450MB
docker-snmp                   Edgecore-SONiC_20220420_052156_ec202012_323   5459484edea4        458MB
docker-snmp                   latest                                        5459484edea4        458MB
docker-sonic-mgmt-framework   Edgecore-SONiC_20220420_052156_ec202012_323   359d0cfafb0a        955MB
docker-sonic-mgmt-framework   latest                                        359d0cfafb0a        955MB
docker-sonic-telemetry        Edgecore-SONiC_20220420_052156_ec202012_323   b15a30271940        515MB
docker-sonic-telemetry        latest                                        b15a30271940        515MB
docker-router-advertiser      Edgecore-SONiC_20220420_052156_ec202012_323   a48462e3711d        410MB
docker-router-advertiser      latest                                        a48462e3711d        410MB

admin@sonic:~$
```
