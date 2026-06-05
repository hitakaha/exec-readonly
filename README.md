# Exec-readonly NSO Package

This NSO package restricts command execution to read-only operations. It is particularly useful when granting users limited access to specific commands via NSO MCP.

## How to Use
Clone, build, and load the package into your NSO environment.

## Supported Platforms
The following operating systems are currently supported:
*   IOS-XR
*   IOS-XE
*   Nexus
*   ASA
*   Huawei

## CLI Usage
To execute a command via the CLI, use the following syntax:

```
devices device c8201 exec-readonly command "ping 192.168.0.1 repeat 1"
```

**Result:**
```
Type escape sequence to abort.
Sending 1, 100-byte ICMP Echos to 192.168.0.1 timeout is 2 seconds:
!
Success rate is 100 percent (1/1)
```

Commands that do not start with `ping`, `show`, or `display` will be rejected:

```
devices device c8201 exec-readonly command "copy run start"
```

**Result:**
```
ERROR: Allowed commands: ping, show, display
```

## MCP Configuration
To expose this package via the NSO MCP function, configure the MCP policy as follows:

```
mcp-server policies rule 1
 action permit
 match path /ncs:devices/device/exec-readonly
```

The following tool will be exposed:
`NSO.ncs_devices_device_exec_readonly`

## How to Customize
To extend the functionality, modify the Python source code to include additional commands or support for other operating systems.  
 

