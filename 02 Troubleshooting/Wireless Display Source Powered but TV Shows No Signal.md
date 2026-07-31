# Wireless Display Source Powered but TV Shows No Signal

tags: #internship #troubleshooting #wireless-display #usb-c #tv #no-signal

## Problem

A smaller screen/device was mounted on a stand and connected through a USB-C dongle or wireless display transmitter. A large TV was supposed to show its output, but the TV showed no usable signal.

The exact source device and exact cause were not confirmed.

## Physical setup

```text
source device / smaller screen
→ USB-C dongle or wireless transmitter
→ TV-side wireless receiver
→ large TV
```

Uncertainty:

- The smaller device may have been a tablet, portable monitor, laptop display, or part of another system.
- Its exact role was not confirmed.

## Symptoms observed

- The smaller screen was powered and lit.
- It showed only an icon resembling two overlapping devices/screens.
- It did not show a normal desktop, login screen, or application interface.
- Pressing its power button did not visibly change the screen.
- The source device could not be restarted normally.
- The TV showed:

```text
No signal, Waiting...
```

- The TV also showed RX and TX counters.
- The dongle connected to the smaller device had a blue indicator light.
- The mentor suspected the source laptop/device rather than the TV.

## What the messages mean

### Lit screen / blue dongle light

This only proves that power was present.

It does **not** prove that:

- the source device finished booting
- the source device was producing video
- USB-C display output was supported
- the transmitter and receiver were paired
- the TV was receiving usable video

### `No signal, Waiting...`

This suggests that the TV/receiver was on but was not receiving a valid video signal from the source side.

### RX / TX counters

These may show receive/transmit activity, but their exact meaning for this device was not confirmed.

## Possible causes

These are hypotheses, not confirmed facts:

1. The laptop/source device was frozen or did not finish booting.
2. The source device was not producing video output.
3. The USB-C connection did not support or did not negotiate display output correctly.
4. The wireless transmitter and receiver had power but were not connected or paired.
5. The dongle, cable, USB-C port, or display driver failed.

## Troubleshooting procedure

1. Disconnect the USB-C dongle and other accessories from the source device.
2. Hold the actual power button continuously for around 15–30 seconds to force shutdown.
3. Wait around 10 seconds.
4. Start the source device again without the dongle attached.
5. Confirm whether its normal desktop or login screen appears.
6. Reconnect the display dongle only after the source device finishes booting.
7. Restart the TV-side receiver as well if necessary.
8. Test the transmitter with another known-working laptop that supports USB-C video output.

## How to isolate the faulty component

### Another laptop works

This points more toward the original laptop/source device:

- frozen system
- unsupported USB-C display output
- faulty USB-C port
- display driver problem

### Another laptop also fails

This points more toward the display system:

- transmitter
- receiver
- pairing
- cable
- power supply

### Original device does not show desktop even without dongle

This points more strongly toward the source device itself rather than the TV.

## Confirmed facts vs uncertain assumptions

### Confirmed observations

- The smaller screen was lit.
- It showed only an overlapping-screen/device icon.
- The TV showed `No signal, Waiting...`.
- RX and TX counters were visible.
- The dongle had a blue light.
- Normal restart was not available.

### Uncertain assumptions

- The smaller device type was not confirmed.
- The mentor suspected the source device, but this was not proven.
- The exact meaning of the icon and RX/TX counters was not confirmed.
- Power indicators did not prove successful boot, pairing, or video transmission.

## Final outcome

**Unresolved.**

The exact failed component and final fix were not confirmed.

## Related notes

- [[Meeting Room Display and HDMI]]
