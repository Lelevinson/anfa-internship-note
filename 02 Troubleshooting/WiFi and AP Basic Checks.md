# WiFi and AP Basic Checks

tags: #internship #troubleshooting #wifi #ap #network

## When this applies

Use this when devices in a room cannot connect to Wi-Fi, connect but have no network, or seem to connect through the wrong access point.

## Main mental model

A Wi-Fi connection has several layers:

```text
Laptop/phone Wi-Fi adapter
→ AP / access point
→ company network switch/router
→ DHCP gives IP address
→ DNS translates names
→ internal system / internet opens
```

So a Wi-Fi problem is not always the AP itself. The problem may be on the device, the AP, the network address system, name resolution, browser settings, or internal-system permission.

## Terms

| Term              | Meaning                                                                                                  |
| ----------------- | -------------------------------------------------------------------------------------------------------- |
| Wi-Fi adapter     | The wireless network card inside the laptop/tablet/phone.                                                |
| AP / Access Point | Device on the ceiling/wall that broadcasts Wi-Fi in a room/area.                                         |
| SSID              | Wi-Fi network name shown in the Wi-Fi list.                                                              |
| Signal strength   | How strong the Wi-Fi signal is. Low signal can connect but still be unstable.                            |
| 2.4 GHz / 5 GHz   | Wi-Fi frequency bands. 2.4 GHz reaches farther but is slower/crowded. 5 GHz is faster but shorter range. |
| Roaming           | Device moving from one AP to another AP with the same SSID. Sometimes the device sticks to a weak AP.    |
| IP address        | Address given to the device so it can talk on the network.                                               |
| DHCP              | Service that automatically gives IP addresses to devices.                                                |
| Gateway           | Network device that sends traffic outside the local network.                                             |
| DNS               | Service that turns names like an internal system name into an IP address.                                |
| Ping              | Basic test to see if a device/server can be reached. Some servers block it.                              |
| Internal system   | Company web/app/service that may only work on company network.                                           |

## First decision: what kind of Wi-Fi problem is it?

### Case A: Wi-Fi option is missing or adapter looks off

Possible cause:

- Wi-Fi adapter disabled
- airplane mode on
- driver/device issue
- old hardware issue

Concrete things to try on Windows:

1. Check airplane mode is off.
2. Turn Wi-Fi off and on.
3. Restart the laptop.
4. Open Settings → Network & internet → Advanced network settings.
5. Check if Wi-Fi adapter is disabled.
6. If disabled, enable it.
7. If still missing, record screenshot and ask mentor/senior.

### Case B: SSID cannot be seen

Possible cause:

- too far from AP
- AP not broadcasting
- device does not support that Wi-Fi band/security
- Wi-Fi adapter problem

Concrete things to try:

1. Move closer to the AP or outside the room.
2. Check if other devices can see the same SSID.
3. Turn Wi-Fi off/on.
4. Restart device.
5. Compare with another laptop/phone.

If many devices cannot see the SSID in the same room, it is more likely AP/room-related.

### Case C: SSID is visible but cannot connect

Possible cause:

- saved Wi-Fi profile is wrong/stale
- account/certificate issue
- device security support issue
- DHCP/network issue after authentication

Concrete things to try on Windows:

1. Disconnect and reconnect.
2. Forget the Wi-Fi profile, then connect again:
   - Settings → Network & internet → Wi-Fi → Manage known networks
   - choose the SSID
   - Forget
   - reconnect
3. Restart the laptop.
4. Check if another device can connect.
5. If it asks for account/certificate/admin permission, do not guess. Ask senior.

### Case D: connected to Wi-Fi but no internet/internal system

Possible cause:

- connected to wrong SSID
- got bad/no IP address
- DHCP issue
- DNS issue
- gateway/network issue
- internal system/browser/permission issue

Concrete things to try:

1. Confirm the SSID is correct.
2. Run:

```powershell
ipconfig
```

Check if Wi-Fi has an IP address.

3. Try renewing IP:

```powershell
ipconfig /release
ipconfig /renew
```

4. Flush DNS:

```powershell
ipconfig /flushdns
```

5. Test DNS:

```powershell
nslookup system-name
```

6. Test web ports if you know the server/system name:

```powershell
Test-NetConnection system-name -Port 80
Test-NetConnection system-name -Port 443
```

7. If normal websites work but internal system fails, check [[IE Mode and Legacy Systems]] and [[Internal System Access Rules]].

### Case E: works outside the room but not inside one room

Possible cause:

- AP in that room has issue
- signal/interference problem
- device is roaming to wrong/weak AP
- room network cable/AP power issue

Concrete things to try:

1. Test with at least two devices in the room.
2. Test the same devices outside the room.
3. Run:

```powershell
netsh wlan show interfaces
```

4. Record SSID, signal percentage, and room number.
5. If all devices fail only in that room, report as likely AP/room issue.

If you are not allowed to touch AP settings, do not try to configure the AP. Collect evidence and escalate.

### Case F: only one old tablet/laptop fails

Possible cause:

- old Wi-Fi adapter
- old Windows/iPad/Android version
- unsupported Wi-Fi security
- weak hardware
- AnyDesk/remote tool compatibility issue

Concrete things to try:

1. Restart device.
2. Forget and reconnect Wi-Fi.
3. Try a different location closer to AP.
4. Compare with a newer device.
5. If old device still fails while others work, record device model and report that it may be hardware/compatibility-related.

## Useful Windows commands

### Show Wi-Fi interface info

```powershell
netsh wlan show interfaces
```

Useful fields:

- SSID
- Signal
- Radio type
- Authentication
- State

### Show IP info

```powershell
ipconfig
ipconfig /all
```

Useful fields:

- IPv4 Address
- Default Gateway
- DNS Servers
- DHCP Enabled

### Renew IP address

```powershell
ipconfig /release
ipconfig /renew
```

Use when connected but network access is broken or IP looks wrong.

### Clear DNS cache

```powershell
ipconfig /flushdns
```

Use when the network works but a system name/site does not resolve correctly.

### Test DNS

```powershell
nslookup system-name
```

Use to check if the PC can translate a server/system name into an IP address.

### Test server and port

```powershell
Test-NetConnection system-name -Port 80
Test-NetConnection system-name -Port 443
```

Use for internal web systems. Port 80 is HTTP. Port 443 is HTTPS.

See [[Basic Network Commands for Support]] for more details.

## Windows settings worth knowing

### Wi-Fi known networks

Path:

```text
Settings → Network & internet → Wi-Fi → Manage known networks
```

Use for:

- forget old Wi-Fi profile
- reconnect cleanly

### Advanced network settings

Path:

```text
Settings → Network & internet → Advanced network settings
```

Use for:

- check adapter status
- enable/disable adapter
- open more adapter options

### Network reset

Path:

```text
Settings → Network & internet → Advanced network settings → Network reset
```

This is more aggressive. It resets network adapters/settings and may require restart. Ask mentor/senior before using on company PCs.

### Proxy settings

Path:

```text
Settings → Network & internet → Proxy
```

Wrong proxy settings can make browsers fail even when Wi-Fi is connected. Do not change company proxy settings without approval. Just know where to check if senior asks.

## Concrete safe-fix order

Try from lowest risk to higher risk:

```text
1. Check correct SSID
2. Airplane mode off
3. Wi-Fi off/on
4. Move closer / test outside room
5. Disconnect/reconnect
6. Forget network and reconnect
7. Restart laptop
8. ipconfig /release and /renew
9. ipconfig /flushdns
10. Disable/enable Wi-Fi adapter
11. Network reset only with approval
12. AP/router/server-side changes only by senior/network admin
```

## How to decide if it is really AP-related

Likely AP/room issue:

- many devices fail in the same room
- same devices work outside the room
- signal is weak/unstable in that room
- issue starts suddenly for all users in that area

Likely device issue:

- only one laptop/tablet fails
- other devices work in the same room
- device is old
- Wi-Fi adapter missing/disabled

Likely internal-system issue:

- internet works
- only one internal site fails
- other internal systems work
- browser mode/IE mode/permission may be involved

Likely DNS/network issue:

- connected to Wi-Fi
- cannot open system by name
- `nslookup` fails
- IP/gateway/DNS looks wrong

## What to record before reporting

- room number
- SSID
- device model
- whether one device or many devices are affected
- whether it works outside the room
- screenshot of Wi-Fi error
- output/screenshot of:

```powershell
netsh wlan show interfaces
ipconfig
nslookup system-name
```

- exact internal system/site if relevant
- time problem happened
- what fixes were already tried

## Notes from internship

- Some old tablets/laptops may fail to connect to Wi-Fi or AnyDesk because the device is too old.
- For AP issues, if you cannot directly change AP settings, collect good evidence and report upward.
- Do not assume every network-looking problem is AP hardware. Browser mode, DNS, permissions, and old devices can look similar from the user side.

## Related notes

- [[Basic Network Commands for Support]]
- [[General IT Support Triage]]
- [[Internal System Access Rules]]
- [[IE Mode and Legacy Systems]]
- [[2026-06-18]]
- [[2026-07-01]]
