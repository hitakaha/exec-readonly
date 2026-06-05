# Exec-readonly package
This is an NSO package which allows only read-only commands which is useful when a user allow certain commands via NSO MCP.

# How to use
Clone the package, make and load the pacakge.

# Supported platforms
Currently, following OS are supported:
- IOS-XR
- IOS-XE
- Nexus
- ASA
- Huawei

# Execute via CLI
Following to how to execute in CLI.

```
# devices device c8201 exec-readonly command "ping 192.168.0.1 repeat 1"                           
result 
Type escape sequence to abort.
Sending 1, 100-byte ICMP Echos to 192.168.0.1 timeout is 2 seconds:
!
Success rate is 100 percent (1/1)
```

If you type a command which does NOT start with "ping", "show" or "display", they are rejected as following.

```
# devices device c8201 exec-readonly command "copy run start"          
result ERROR: Allowed commands: ping, show
```

# MCP configuration
To expose this package via NSO MCP function, configure MCP policy as follows.

```
mcp-server policies rule 1
 action permit
 match path /ncs:devices/device/exec-readonly
```


Following new Tool is exposed.

```
NSO.ncs_devices_device_exec_readonly   
```

# How to customize
Check the python code and add any more comomands or OS.

