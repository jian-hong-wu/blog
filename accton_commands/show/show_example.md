# show

### change the port speed (Ethernet48 port to 40G, Ethernet2 to 10G)
```
admin@sonic:~$ show interfaces status Ethernet2
  Interface    Lanes    Speed    MTU    FEC          Alias    Vlan    Oper    Admin            Type    Asym PFC    Oper Speed
-----------  -------  -------  -----  -----  -------------  ------  ------  -------  --------------  ----------  ------------
  Ethernet2        4      25G   9100   none  Eth6/4(Port3)  routed    down       up  SFP/SFP+/SFP28         N/A           25G
admin@sonic:~$
admin@sonic:~$ # change the port speed to 1000G
admin@sonic:~$ sudo config interface speed Ethernet2 1000000

Can't set the port speed. Only support port speed: 25000.
admin@sonic:~$
admin@sonic:~$ # change the port speed to 10G
admin@sonic:~$ sudo config interface speed Ethernet2 10000

Due to the special circuit scheme on PCB of this device, the port specified
in the command is one of the child port out of 4 internally broken out ports.
To change port speed as 1G or 10G, you must use "config interface breakout"
command to change the port breakout mode as "4x10G[1G]". This will change
port speed as 10G upon 4 ports at the same time. Under "4x10G[1G]" breakout mode,
it is allowed to use "config interface speed" command to set port speed upon
any port out of those 4 ports as 1G or 10G.

admin@sonic:~$
admin@sonic:~$
admin@sonic:~$ show interfaces status Ethernet48
  Interface        Lanes    Speed    MTU    FEC            Alias    Vlan    Oper    Admin             Type    Asym PFC    Oper Speed
-----------  -----------  -------  -----  -----  ---------------  ------  ------  -------  ---------------  ----------  ------------
 Ethernet48  77,78,79,80     100G   9100   none  Eth49/1(Port49)  routed    down       up  QSFP28 or later         N/A          100G
admin@sonic:~$
admin@sonic:~$
admin@sonic:~$ sudo config interface speed Ethernet48 10000

Can't set the port speed. Only support port speed: 40000, 100000.
admin@sonic:~$ sudo config interface speed Ethernet48 40000
admin@sonic:~$ show interfaces status Ethernet48
  Interface        Lanes    Speed    MTU    FEC            Alias    Vlan    Oper    Admin             Type    Asym PFC    Oper Speed
-----------  -----------  -------  -----  -----  ---------------  ------  ------  -------  ---------------  ----------  ------------
 Ethernet48  77,78,79,80      40G   9100   none  Eth49/1(Port49)  routed      up       up  QSFP28 or later         N/A           40G
admin@sonic:~$
admin@sonic:~$ sudo config save
Existing files will be overwritten, continue? [y/N]: y
Running command: /usr/local/bin/sonic-cfggen -d --print-data > /etc/sonic/config_db.json
admin@sonic:~$
```

### config_db.json
admin@sonic:~$ **cat /etc/sonic/config_db.json**
(note: Ethernet port order is listed alphabetically, ~1, ~10, ~11, ..., ~2, ~20, ~21, etc ...) 
```
admin@sonic:~$ cat /etc/sonic/config_db.json
{
    "BREAKOUT_CFG": {
        "Ethernet10": {
            "brkout_mode": "4x25G"
        },
        "Ethernet17": {
            "brkout_mode": "4x25G"
        },
        "Ethernet18": {
            "brkout_mode": "4x25G"
        },
        "Ethernet22": {
            "brkout_mode": "4x25G"
        },
        "Ethernet29": {
            "brkout_mode": "4x25G"
        },
        "Ethernet30": {
            "brkout_mode": "4x25G"
        },
        "Ethernet34": {
            "brkout_mode": "4x25G"
        },
        "Ethernet39": {
            "brkout_mode": "4x25G"
        },
        "Ethernet41": {
            "brkout_mode": "4x25G"
        },
        "Ethernet43": {
            "brkout_mode": "4x25G"
        },
        "Ethernet48": {
            "brkout_mode": "1x100G[40G]"
        },
        "Ethernet5": {
            "brkout_mode": "4x25G"
        },
        "Ethernet52": {
            "brkout_mode": "1x100G[40G]"
        },
        "Ethernet56": {
            "brkout_mode": "1x100G[40G]"
        },
        "Ethernet6": {
            "brkout_mode": "4x25G"
        },
        "Ethernet60": {
            "brkout_mode": "1x100G[40G]"
        },
        "Ethernet64": {
            "brkout_mode": "1x100G[40G]"
        },
        "Ethernet68": {
            "brkout_mode": "1x100G[40G]"
        },
        "Ethernet72": {
            "brkout_mode": "1x100G[40G]"
        },
        "Ethernet76": {
            "brkout_mode": "1x100G[40G]"
        }
    },
    "CRM": {
        "Config": {
            "acl_counter_high_threshold": "85",
            "acl_counter_low_threshold": "70",
            "acl_counter_threshold_type": "percentage",
            "acl_entry_high_threshold": "85",
            "acl_entry_low_threshold": "70",
            "acl_entry_threshold_type": "percentage",
            "acl_group_high_threshold": "85",
            "acl_group_low_threshold": "70",
            "acl_group_threshold_type": "percentage",
            "acl_table_high_threshold": "85",
            "acl_table_low_threshold": "70",
            "acl_table_threshold_type": "percentage",
            "dnat_entry_high_threshold": "85",
            "dnat_entry_low_threshold": "70",
            "dnat_entry_threshold_type": "percentage",
            "fdb_entry_high_threshold": "85",
            "fdb_entry_low_threshold": "70",
            "fdb_entry_threshold_type": "percentage",
            "ipmc_entry_high_threshold": "85",
            "ipmc_entry_low_threshold": "70",
            "ipmc_entry_threshold_type": "percentage",
            "ipv4_neighbor_high_threshold": "85",
            "ipv4_neighbor_low_threshold": "70",
            "ipv4_neighbor_threshold_type": "percentage",
            "ipv4_nexthop_high_threshold": "85",
            "ipv4_nexthop_low_threshold": "70",
            "ipv4_nexthop_threshold_type": "percentage",
            "ipv4_route_high_threshold": "85",
            "ipv4_route_low_threshold": "70",
            "ipv4_route_threshold_type": "percentage",
            "ipv6_neighbor_high_threshold": "85",
            "ipv6_neighbor_low_threshold": "70",
            "ipv6_neighbor_threshold_type": "percentage",
            "ipv6_nexthop_high_threshold": "85",
            "ipv6_nexthop_low_threshold": "70",
            "ipv6_nexthop_threshold_type": "percentage",
            "ipv6_route_high_threshold": "85",
            "ipv6_route_low_threshold": "70",
            "ipv6_route_threshold_type": "percentage",
            "nexthop_group_high_threshold": "85",
            "nexthop_group_low_threshold": "70",
            "nexthop_group_member_high_threshold": "85",
            "nexthop_group_member_low_threshold": "70",
            "nexthop_group_member_threshold_type": "percentage",
            "nexthop_group_threshold_type": "percentage",
            "polling_interval": "300",
            "snat_entry_high_threshold": "85",
            "snat_entry_low_threshold": "70",
            "snat_entry_threshold_type": "percentage"
        }
    },
    "DEVICE_METADATA": {
        "localhost": {
            "buffer_model": "traditional",
            "default_bgp_status": "up",
            "default_pfcwd_status": "disable",
            "docker_routing_config_mode": "split",
            "frr_mgmt_framework_config": "true",
            "hostname": "sonic",
            "hwsku": "Accton-AS7326-56X",
            "mac": "68:21:5f:4f:c7:30",
            "platform": "x86_64-accton_as7326_56x-r0",
            "type": "LeafRouter"
        }
    },
    "FEATURE": {
        "bgp": {
            "auto_restart": "enabled",
            "has_global_scope": "False",
            "has_per_asic_scope": "True",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "database": {
            "auto_restart": "always_enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "True",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "always_enabled"
        },
        "dhcp_relay": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "iccpd": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "lldp": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "True",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "mgmt-framework": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "True",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "nat": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "pmon": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "radv": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "sflow": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "snmp": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "True",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "stp": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "swss": {
            "auto_restart": "enabled",
            "has_global_scope": "False",
            "has_per_asic_scope": "True",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "syncd": {
            "auto_restart": "enabled",
            "has_global_scope": "False",
            "has_per_asic_scope": "True",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "teamd": {
            "auto_restart": "enabled",
            "has_global_scope": "False",
            "has_per_asic_scope": "True",
            "has_timer": "False",
            "high_mem_alert": "disabled",
            "state": "enabled"
        },
        "telemetry": {
            "auto_restart": "enabled",
            "has_global_scope": "True",
            "has_per_asic_scope": "False",
            "has_timer": "True",
            "high_mem_alert": "disabled",
            "state": "enabled"
        }
    },
    "FLEX_COUNTER_TABLE": {
        "BUFFER_POOL_WATERMARK": {
            "FLEX_COUNTER_STATUS": "enable"
        },
        "PFCWD": {
            "FLEX_COUNTER_STATUS": "enable"
        },
        "PG_DROP": {
            "FLEX_COUNTER_STATUS": "enable"
        },
        "PG_WATERMARK": {
            "FLEX_COUNTER_STATUS": "enable"
        },
        "PORT": {
            "FLEX_COUNTER_STATUS": "enable"
        },
        "PORT_BUFFER_DROP": {
            "FLEX_COUNTER_STATUS": "enable"
        },
        "QUEUE": {
            "FLEX_COUNTER_STATUS": "enable"
        },
        "QUEUE_WATERMARK": {
            "FLEX_COUNTER_STATUS": "enable"
        },
        "RIF": {
            "FLEX_COUNTER_STATUS": "enable"
        }
    },
    "INTERFACE": {
        "Ethernet48": {},
        "Ethernet48|10.0.0.1/31": {}
    },
    "KDUMP": {
        "config": {
            "enabled": "false",
            "memory": "0M-2G:256M,2G-4G:320M,4G-8G:384M,8G-:448M",
            "num_dumps": "3"
        }
    },
    "LOOPBACK_INTERFACE": {
        "Loopback0": {},
        "Loopback0|2.2.2.2/32": {}
    },
    "PORT": {
        "Ethernet0": {
            "admin_status": "up",
            "alias": "Eth6/3(Port1)",
            "index": "1",
            "lanes": "3",
            "mtu": "9100",
            "parent_port": "Ethernet5",
            "speed": "25000"
        },
        "Ethernet1": {
            "admin_status": "up",
            "alias": "Eth6/2(Port2)",
            "index": "2",
            "lanes": "2",
            "mtu": "9100",
            "parent_port": "Ethernet5",
            "speed": "25000"
        },
        "Ethernet10": {
            "admin_status": "up",
            "alias": "Eth11/1(Port11)",
            "index": "11",
            "lanes": "13",
            "mtu": "9100",
            "parent_port": "Ethernet10",
            "speed": "25000"
        },
        "Ethernet11": {
            "admin_status": "up",
            "alias": "Eth11/3(Port12)",
            "index": "12",
            "lanes": "15",
            "mtu": "9100",
            "parent_port": "Ethernet10",
            "speed": "25000"
        },
        "Ethernet12": {
            "admin_status": "up",
            "alias": "Eth18/3(Port13)",
            "index": "13",
            "lanes": "23",
            "mtu": "9100",
            "parent_port": "Ethernet17",
            "speed": "25000"
        },
        "Ethernet13": {
            "admin_status": "up",
            "alias": "Eth18/2(Port14)",
            "index": "14",
            "lanes": "22",
            "mtu": "9100",
            "parent_port": "Ethernet17",
            "speed": "25000"
        },
        "Ethernet14": {
            "admin_status": "up",
            "alias": "Eth18/4(Port15)",
            "index": "15",
            "lanes": "24",
            "mtu": "9100",
            "parent_port": "Ethernet17",
            "speed": "25000"
        },
        "Ethernet15": {
            "admin_status": "up",
            "alias": "Eth19/4(Port16)",
            "index": "16",
            "lanes": "32",
            "mtu": "9100",
            "parent_port": "Ethernet18",
            "speed": "25000"
        },
        "Ethernet16": {
            "admin_status": "up",
            "alias": "Eth19/3(Port17)",
            "index": "17",
            "lanes": "31",
            "mtu": "9100",
            "parent_port": "Ethernet18",
            "speed": "25000"
        },
        "Ethernet17": {
            "admin_status": "up",
            "alias": "Eth18/1(Port18)",
            "index": "18",
            "lanes": "21",
            "mtu": "9100",
            "parent_port": "Ethernet17",
            "speed": "25000"
        },
        "Ethernet18": {
            "admin_status": "up",
            "alias": "Eth19/1(Port19)",
            "index": "19",
            "lanes": "29",
            "mtu": "9100",
            "parent_port": "Ethernet18",
            "speed": "25000"
        },
        "Ethernet19": {
            "admin_status": "up",
            "alias": "Eth23/4(Port20)",
            "index": "20",
            "lanes": "36",
            "mtu": "9100",
            "parent_port": "Ethernet22",
            "speed": "25000"
        },
        "Ethernet2": {
            "admin_status": "up",
            "alias": "Eth6/4(Port3)",
            "index": "3",
            "lanes": "4",
            "mtu": "9100",
            "parent_port": "Ethernet5",
            "speed": "25000"
        },
        "Ethernet20": {
            "admin_status": "up",
            "alias": "Eth19/2(Port21)",
            "index": "21",
            "lanes": "30",
            "mtu": "9100",
            "parent_port": "Ethernet18",
            "speed": "25000"
        },
        "Ethernet21": {
            "admin_status": "up",
            "alias": "Eth23/2(Port22)",
            "index": "22",
            "lanes": "34",
            "mtu": "9100",
            "parent_port": "Ethernet22",
            "speed": "25000"
        },
        "Ethernet22": {
            "admin_status": "up",
            "alias": "Eth23/1(Port23)",
            "index": "23",
            "lanes": "33",
            "mtu": "9100",
            "parent_port": "Ethernet22",
            "speed": "25000"
        },
        "Ethernet23": {
            "admin_status": "up",
            "alias": "Eth23/3(Port24)",
            "index": "24",
            "lanes": "35",
            "mtu": "9100",
            "parent_port": "Ethernet22",
            "speed": "25000"
        },
        "Ethernet24": {
            "admin_status": "up",
            "alias": "Eth30/3(Port25)",
            "index": "25",
            "lanes": "43",
            "mtu": "9100",
            "parent_port": "Ethernet29",
            "speed": "25000"
        },
        "Ethernet25": {
            "admin_status": "up",
            "alias": "Eth30/2(Port26)",
            "index": "26",
            "lanes": "42",
            "mtu": "9100",
            "parent_port": "Ethernet29",
            "speed": "25000"
        },
        "Ethernet26": {
            "admin_status": "up",
            "alias": "Eth30/4(Port27)",
            "index": "27",
            "lanes": "44",
            "mtu": "9100",
            "parent_port": "Ethernet29",
            "speed": "25000"
        },
        "Ethernet27": {
            "admin_status": "up",
            "alias": "Eth31/4(Port28)",
            "index": "28",
            "lanes": "52",
            "mtu": "9100",
            "parent_port": "Ethernet30",
            "speed": "25000"
        },
        "Ethernet28": {
            "admin_status": "up",
            "alias": "Eth31/3(Port29)",
            "index": "29",
            "lanes": "51",
            "mtu": "9100",
            "parent_port": "Ethernet30",
            "speed": "25000"
        },
        "Ethernet29": {
            "admin_status": "up",
            "alias": "Eth30/1(Port30)",
            "index": "30",
            "lanes": "41",
            "mtu": "9100",
            "parent_port": "Ethernet29",
            "speed": "25000"
        },
        "Ethernet3": {
            "admin_status": "up",
            "alias": "Eth7/4(Port4)",
            "index": "4",
            "lanes": "8",
            "mtu": "9100",
            "parent_port": "Ethernet6",
            "speed": "25000"
        },
        "Ethernet30": {
            "admin_status": "up",
            "alias": "Eth31/1(Port31)",
            "index": "31",
            "lanes": "49",
            "mtu": "9100",
            "parent_port": "Ethernet30",
            "speed": "25000"
        },
        "Ethernet31": {
            "admin_status": "up",
            "alias": "Eth35/4(Port32)",
            "index": "32",
            "lanes": "60",
            "mtu": "9100",
            "parent_port": "Ethernet34",
            "speed": "25000"
        },
        "Ethernet32": {
            "admin_status": "up",
            "alias": "Eth31/2(Port33)",
            "index": "33",
            "lanes": "50",
            "mtu": "9100",
            "parent_port": "Ethernet30",
            "speed": "25000"
        },
        "Ethernet33": {
            "admin_status": "up",
            "alias": "Eth35/2(Port34)",
            "index": "34",
            "lanes": "58",
            "mtu": "9100",
            "parent_port": "Ethernet34",
            "speed": "25000"
        },
        "Ethernet34": {
            "admin_status": "up",
            "alias": "Eth35/1(Port35)",
            "index": "35",
            "lanes": "57",
            "mtu": "9100",
            "parent_port": "Ethernet34",
            "speed": "25000"
        },
        "Ethernet35": {
            "admin_status": "up",
            "alias": "Eth35/3(Port36)",
            "index": "36",
            "lanes": "59",
            "mtu": "9100",
            "parent_port": "Ethernet34",
            "speed": "25000"
        },
        "Ethernet36": {
            "admin_status": "up",
            "alias": "Eth42/2(Port37)",
            "index": "37",
            "lanes": "62",
            "mtu": "9100",
            "parent_port": "Ethernet41",
            "speed": "25000"
        },
        "Ethernet37": {
            "admin_status": "up",
            "alias": "Eth42/3(Port38)",
            "index": "38",
            "lanes": "63",
            "mtu": "9100",
            "parent_port": "Ethernet41",
            "speed": "25000"
        },
        "Ethernet38": {
            "admin_status": "up",
            "alias": "Eth42/4(Port39)",
            "index": "39",
            "lanes": "64",
            "mtu": "9100",
            "parent_port": "Ethernet41",
            "speed": "25000"
        },
        "Ethernet39": {
            "admin_status": "up",
            "alias": "Eth40/1(Port40)",
            "index": "40",
            "lanes": "65",
            "mtu": "9100",
            "parent_port": "Ethernet39",
            "speed": "25000"
        },
        "Ethernet4": {
            "admin_status": "down",
            "alias": "Eth7/3(Port5)",
            "index": "5",
            "lanes": "7",
            "mtu": "9100",
            "parent_port": "Ethernet6",
            "speed": "25000"
        },
        "Ethernet40": {
            "admin_status": "up",
            "alias": "Eth40/2(Port41)",
            "index": "41",
            "lanes": "66",
            "mtu": "9100",
            "parent_port": "Ethernet39",
            "speed": "25000"
        },
        "Ethernet41": {
            "admin_status": "up",
            "alias": "Eth42/1(Port42)",
            "index": "42",
            "lanes": "61",
            "mtu": "9100",
            "parent_port": "Ethernet41",
            "speed": "25000"
        },
        "Ethernet42": {
            "admin_status": "up",
            "alias": "Eth40/4(Port43)",
            "index": "43",
            "lanes": "68",
            "mtu": "9100",
            "parent_port": "Ethernet39",
            "speed": "25000"
        },
        "Ethernet43": {
            "admin_status": "up",
            "alias": "Eth44/1(Port44)",
            "index": "44",
            "lanes": "69",
            "mtu": "9100",
            "parent_port": "Ethernet43",
            "speed": "25000"
        },
        "Ethernet44": {
            "admin_status": "up",
            "alias": "Eth40/3(Port45)",
            "index": "45",
            "lanes": "67",
            "mtu": "9100",
            "parent_port": "Ethernet39",
            "speed": "25000"
        },
        "Ethernet45": {
            "admin_status": "up",
            "alias": "Eth44/3(Port46)",
            "index": "46",
            "lanes": "71",
            "mtu": "9100",
            "parent_port": "Ethernet43",
            "speed": "25000"
        },
        "Ethernet46": {
            "admin_status": "up",
            "alias": "Eth44/4(Port47)",
            "index": "47",
            "lanes": "72",
            "mtu": "9100",
            "parent_port": "Ethernet43",
            "speed": "25000"
        },
        "Ethernet47": {
            "admin_status": "up",
            "alias": "Eth44/2(Port48)",
            "index": "48",
            "lanes": "70",
            "mtu": "9100",
            "parent_port": "Ethernet43",
            "speed": "25000"
        },
        "Ethernet48": {
            "admin_status": "up",
            "alias": "Eth49/1(Port49)",
            "index": "49",
            "lanes": "77,78,79,80",
            "mtu": "9100",
            "parent_port": "Ethernet48",
            "speed": "40000"
        },
        "Ethernet5": {
            "admin_status": "up",
            "alias": "Eth6/1(Port6)",
            "index": "6",
            "lanes": "1",
            "mtu": "9100",
            "parent_port": "Ethernet5",
            "speed": "25000"
        },
        "Ethernet52": {
            "admin_status": "up",
            "alias": "Eth50/1(Port50)",
            "index": "50",
            "lanes": "85,86,87,88",
            "mtu": "9100",
            "parent_port": "Ethernet52",
            "speed": "100000"
        },
        "Ethernet56": {
            "admin_status": "up",
            "alias": "Eth51/1(Port51)",
            "index": "51",
            "lanes": "93,94,95,96",
            "mtu": "9100",
            "parent_port": "Ethernet56",
            "speed": "100000"
        },
        "Ethernet6": {
            "admin_status": "up",
            "alias": "Eth7/1(Port7)",
            "index": "7",
            "lanes": "5",
            "mtu": "9100",
            "parent_port": "Ethernet6",
            "speed": "25000"
        },
        "Ethernet60": {
            "admin_status": "up",
            "alias": "Eth52/1(Port52)",
            "index": "52",
            "lanes": "97,98,99,100",
            "mtu": "9100",
            "parent_port": "Ethernet60",
            "speed": "100000"
        },
        "Ethernet64": {
            "admin_status": "up",
            "alias": "Eth53/1(Port53)",
            "index": "53",
            "lanes": "105,106,107,108",
            "mtu": "9100",
            "parent_port": "Ethernet64",
            "speed": "100000"
        },
        "Ethernet68": {
            "admin_status": "up",
            "alias": "Eth54/1(Port54)",
            "index": "54",
            "lanes": "113,114,115,116",
            "mtu": "9100",
            "parent_port": "Ethernet68",
            "speed": "100000"
        },
        "Ethernet7": {
            "admin_status": "up",
            "alias": "Eth11/4(Port8)",
            "index": "8",
            "lanes": "16",
            "mtu": "9100",
            "parent_port": "Ethernet10",
            "speed": "25000"
        },
        "Ethernet72": {
            "admin_status": "up",
            "alias": "Eth55/1(Port55)",
            "index": "55",
            "lanes": "121,122,123,124",
            "mtu": "9100",
            "parent_port": "Ethernet72",
            "speed": "100000"
        },
        "Ethernet76": {
            "admin_status": "up",
            "alias": "Eth56/1(Port56)",
            "index": "56",
            "lanes": "125,126,127,128",
            "mtu": "9100",
            "parent_port": "Ethernet76",
            "speed": "100000"
        },
        "Ethernet8": {
            "admin_status": "up",
            "alias": "Eth7/2(Port9)",
            "index": "9",
            "lanes": "6",
            "mtu": "9100",
            "parent_port": "Ethernet6",
            "speed": "25000"
        },
        "Ethernet9": {
            "admin_status": "up",
            "alias": "Eth11/2(Port10)",
            "index": "10",
            "lanes": "14",
            "mtu": "9100",
            "parent_port": "Ethernet10",
            "speed": "25000"
        }
    },
    "REST_SERVER": {
        "default": {
            "client_auth": "user"
        }
    },
    "SNMP": {
        "LOCATION": {
            "Location": "public"
        }
    },
    "SNMP_COMMUNITY": {
        "public": {
            "TYPE": "RO"
        }
    },
    "VERSIONS": {
        "DATABASE": {
            "VERSION": "version_2_0_1"
        }
    },
    "VLAN": {
        "Vlan30": {
            "vlanid": "30"
        },
        "Vlan4": {
            "vlanid": "4"
        }
    },
    "VLAN_MEMBER": {
        "Vlan30|Ethernet52": {
            "tagging_mode": "tagged"
        },
        "Vlan4|Ethernet6": {
            "tagging_mode": "tagged"
        },
        "Vlan4|Ethernet7": {
            "tagging_mode": "untagged"
        }
    },
    "VXLAN_EVPN_NVO": {
        "nvo": {
            "source_vtep": "vtep"
        }
    },
    "VXLAN_TUNNEL": {
        "vtep": {
            "src_ip": "2.2.2.2"
        }
    },
    "VXLAN_TUNNEL_MAP": {
        "vtep|map_3000_Vlan30": {
            "vlan": "Vlan30",
            "vni": "3000"
        }
    }
}
admin@sonic:~$
```
