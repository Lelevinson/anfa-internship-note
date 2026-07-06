# Meeting Room Display and HDMI

tags: #internship #troubleshooting #meeting-room #hdmi #usb-c

## When this applies

Use this when a meeting room display/projector/TV cannot share screen even though the HDMI source looks correct.

## Main idea

Meeting-room screen sharing can fail for different reasons:

```text
TV/input source problem
screen-sharing receiver problem
laptop USB-C limitation
HDMI cable/source problem
```

Do not assume every case needs unplug/replug. First check what the TV is showing.

## Terms

| Term | Meaning |
|---|---|
| 會議室 | huìyìshì, meeting room |
| 輸入來源 | shūrù láiyuán, input source |
| HDMI | Common video cable/port for screen output |
| USB Type-C | Small reversible port; not every Type-C port supports video/display output |
| Screen-sharing receiver | Device used for screen sharing from the laptop to the TV |
| Standby screen | TV/device waiting screen, meaning the display receiver is on and ready |

## Important USB-C note

Some laptops have a USB Type-C port that **does not support display/screen sharing**.

Clue:

```text
TV already shows the standby screen
but laptop does not share anything
```

Meaning:

- TV/display receiver is probably already ready.
- The problem may be the laptop USB-C port.
- Some Type-C ports only support charging/data, not display output.

In this case, usually do **not** need to repeatedly unplug and plug back in.

Use the table HDMI cable instead.

## Decision flow

### Case A: TV already shows standby screen, but laptop does not share

Likely cause:

- laptop USB Type-C port does not support display output or this screen-sharing device

Try:

1. Confirm TV is on the standby screen.
2. Confirm the screen-sharing receiver is connected to the laptop.
3. If nothing shares, do not keep repeating unplug/replug.
4. Use the HDMI cable on the table.
5. If needed, unplug/replug once only to show/confirm the unsupported Type-C error.

### Case B: TV is not on standby screen

Likely cause:

- wrong input source
- receiver not detected
- HDMI/source mismatch
- sharing device not initialized correctly

Try:

1. Check TV input source.
2. Try the correct HDMI input.
3. Unplug and plug back in the receiver if needed.
4. Wait for the standby screen.
5. Test sharing again.

### Case C: HDMI table cable works

If wireless/Type-C does not work but HDMI table cable works, record that the workaround is HDMI.

This suggests:

- meeting-room TV/display is working
- laptop can output through HDMI
- the issue is likely Type-C/screen-sharing compatibility, not the TV itself

## Observed fix: HDMI source already set but screen sharing fails

Problem:

- 會議室 is already on HDMI2, but screen sharing does not work.

Try:

1. Unplug the rear HDMI first.
2. Change HDMI option first, for example to HDMI 3.
3. Plug the screen-sharing receiver into the user's laptop/device.
4. Plug the rear HDMI back in.
5. Test sharing again.

## Receiver note

- The 會議室 screen-sharing receiver does not need to be plugged into the main machine.
- It should be plugged into the user's laptop/device.

## Related issue: iPad YouTube not playing

Possible fix:

- Change 輸入來源 / input source to HDMI 4.
- The issue may be related to AirPlay blocking or source mismatch.

## Safe troubleshooting order

```text
1. Check what the TV shows.
2. If standby screen is showing, suspect laptop/USB-C side.
3. If standby screen is not showing, check input source and receiver connection.
4. Try HDMI cable on the table as a stable workaround.
5. Avoid repeatedly unplugging/replugging if the clue points to unsupported Type-C.
```

## Escalation info to collect

- room number
- current input source
- whether standby screen is showing
- laptop model if known
- whether connection is USB-C receiver or HDMI
- whether HDMI table cable works
- photos of current setup
- what source/input was tested

## Related daily logs

- [[2026-06-18]]
- [[2026-06-26]]
- [[2026-06-30]]
- [[2026-07-06]]
