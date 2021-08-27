[上一頁](/blog/sonic_command/layer2/show/)

### Show platform & environments

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
$ show environment
---
<pre>admin@sonic:~$ show environment
Error response from daemon: Container 75078ce1ed609c70e6992927281373135268d09dead3ce932b3dfad464f4ceb0 is not running
admin@sonic:~$ </pre>
---




