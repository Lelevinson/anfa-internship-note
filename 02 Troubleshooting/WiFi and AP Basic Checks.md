# WiFi and AP Basic Checks

tags: #internship #troubleshooting #wifi #ap #network

## When this applies

Use this when devices in a room cannot connect to Wi-Fi or seem to connect through the wrong access point.

## Useful Windows command

```powershell
netsh wlan show interfaces
```

This can show basic Wi-Fi interface information such as connected SSID, signal, and radio details.

## Basic support flow

1. Confirm scope:
   - only one device?
   - all devices in the room?
   - only this room?
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

## Notes from internship

- Some old tablets/laptops may fail to connect to Wi-Fi or AnyDesk because the device is too old.
- For AP issues, if you cannot directly change AP settings, collect good evidence and report upward.

## Related daily logs

- [[2026-06-18]]
- [[2026-07-01]]
