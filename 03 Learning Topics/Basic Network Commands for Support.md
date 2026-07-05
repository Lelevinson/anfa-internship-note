# Basic Network Commands for Support

tags: #internship #learning #network #windows #support

## Main idea

Network commands help you answer simple questions before escalating:

```text
Am I connected?
Can I reach the server?
Is DNS resolving the name?
Is the port open?
Which Wi-Fi/AP am I connected to?
```

## Useful commands

### ipconfig

```powershell
ipconfig
ipconfig /all
```

Use for:

- checking IP address
- checking gateway
- checking DNS server
- checking whether the adapter has a normal address

### ping

```powershell
ping server-name
ping 8.8.8.8
```

Use for basic reachability. But remember: some servers block ping, so failed ping does not always mean the server is down.

### nslookup

```powershell
nslookup system-name
```

Use for DNS/name resolution.

Question it answers:

```text
Can this PC translate the system name into an IP address?
```

### Test-NetConnection

```powershell
Test-NetConnection server-name
Test-NetConnection server-name -Port 80
Test-NetConnection server-name -Port 443
```

Use for checking whether a server/port is reachable.

Common ports:

| Port | Meaning |
|---|---|
| 80 | HTTP |
| 443 | HTTPS |
| 21 | FTP |
| 3389 | Remote Desktop |

### netsh wlan show interfaces

```powershell
netsh wlan show interfaces
```

Use for Wi-Fi/AP checks.

Can help show:

- connected SSID
- signal strength
- Wi-Fi adapter info
- basic connection state

## How to think through a web-system problem

Example: internal web page cannot open.

```text
1. Is the PC connected to company network?
2. Does DNS resolve the name? → nslookup
3. Can the PC reach HTTP/HTTPS port? → Test-NetConnection
4. Is the URL http or https?
5. Is it a browser/IE Mode problem instead?
```

## What to record

- command used
- result screenshot/text
- exact system name or URL
- PC/user affected
- whether another PC works

## Related notes

- [[WiFi and AP Basic Checks]]
- [[IE Mode and Legacy Systems]]
- [[Internal System Access Rules]]
- [[General IT Support Triage]]
