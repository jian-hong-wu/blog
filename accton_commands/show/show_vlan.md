# show vlan command

### show vlan config
admin@sonic:~$ **show vlan config**
```
admin@sonic:~$ show vlan config
Name      VID  Member      Mode
------  -----  ----------  --------
Vlan4       4  Ethernet6   tagged
Vlan4       4  Ethernet7   untagged
Vlan30     30  Ethernet52  tagged
```

### show vlan brief
admin@sonic:~$ **show vlan brief**
```
admin@sonic:~$ show vlan brief
+-----------+--------------+------------+----------------+---------------+---------------+-------------+-------------+
|   VLAN ID | IP Address   | Ports      | Port Tagging   | DHCP Helper   | DHCP Source   | DHCP Link   | Proxy ARP   |
|           |              |            |                | Address       | Interface     | Selection   |             |
+===========+==============+============+================+===============+===============+=============+=============+
|         4 |              | Ethernet6  | tagged         |               |               |             | disabled    |
|           |              | Ethernet7  | untagged       |               |               |             |             |
+-----------+--------------+------------+----------------+---------------+---------------+-------------+-------------+
|        30 |              | Ethernet52 | tagged         |               |               |             | disabled    |
+-----------+--------------+------------+----------------+---------------+---------------+-------------+-------------+
admin@sonic:~$
```

### show vlan
admin@sonic:~$ **show vlan**
```
admin@sonic:~$ show vlan
Usage: show vlan [OPTIONS] COMMAND [ARGS]...

  Show VLAN information

Options:
  -h, -?, --help  Show this message and exit.

Commands:
  brief   Show all bridge information
  config
```
