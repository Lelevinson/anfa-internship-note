# WiFi and AP Basic Checks

tags: #internship #troubleshooting #wifi #ap #network

## When this applies

Use this when devices in a room cannot connect to Wi-Fi or seem to connect through the wrong access point.

## Main idea

A Wi-Fi problem can be:

```text
one device problem
one room/AP problem
network/DHCP/DNS problem
account/login problem
old hardware problem
```

Before trying to fix the AP, identify the scope.

## Useful Windows command

```powershell
netsh wlan show interfaces
```

This can show basic Wi-Fi interface information such as connected SSID, signal, and radio details.

See [[Basic Network Commands for Support]] for more commands.

## Basic support flow

1. Confirm scope:
   - only one device?
   - all devices in the room?
   - only this room?
   - only one SSID?
2. Confirm whether other nearby areas work.
3. Check whether the affected device can see the SSID.
4. Check whether it connects but has no network access.
5. Run:

```powershell
netsh wlan show interfaces
```

6. Record:
   - room number
   - device model
   - SSID
   - time of issue
   - screenshot of error
   - whether other users are affected

## How to think about AP problems

If every device in one room has trouble, it may be room/AP-related.

If only one old device has trouble, it may be device-related.

If the device connects but cannot open internal systems, it may be network/DNS/permission/browser-related instead of AP hardware.

## Safe checks before reporting

- Try another nearby location.
- Compare with another laptop/phone.
- Confirm SSID.
- Check signal level.
- Record the room and time.
- Screenshot the error.

## Notes from internship

- Some old tablets/laptops may fail to connect to Wi-Fi or AnyDesk because the device is too old.
- For AP issues, if you cannot directly change AP settings, collect good evidence and report upward.

## Related daily logs

- [[Basic Network Commands for Support]]
- [[General IT Support Triage]]
- [[2026-06-18]]
- [[2026-07-01]]
