# Install Fuji Xerox Network Printers on a New Laptop

tags: #internship #troubleshooting #printer #fuji-xerox #windows #network-printer

## Purpose

Use this when setting up the two company Fuji Xerox network printers on a new employee laptop.

## Confirmed printer information

The printer-driver folders are located at:

```text
Network
→ 192.168.0.166
→ mis共用
→ 1_軟體
→ 03_印表機驅動程式
```

### 27F printer

```text
Folder:
27F_事務機_FujiXerox ApeosPort-VI C5571_192.168.0.232_win

Model:
Fuji Xerox ApeosPort-VI C5571

IP:
192.168.0.232

Installer remembered from previous note:
launcher.exe
```

### 30F printer

```text
Folder:
30F_事務機_FujiXerox ApeosPort-VI C3370_192.168.0.233_win_x64

Model:
Fuji Xerox ApeosPort-VI C3370

IP:
192.168.0.233

Installer remembered from previous note:
setup.exe
```

The image also shows macOS driver folders, but use the Windows folders for company Windows laptops.

## Where to verify company information

Current remembered locations:

```text
MIS 公用 network folder
→ 常用 IP address
→ IP 分配表
```

Exact location is still forgotten.

For the internal installation manual:

```text
MIS 公用 network folder
→ Gino folder
→ look for a file ending in 手冊
```

Exact manual file name is still forgotten.

## Terms

| Term | Meaning |
|---|---|
| Driver | Software that lets Windows communicate correctly with the printer model. |
| Network printer | A printer reached through the company network instead of directly by USB. |
| IP address | Network address of the printer, such as `192.168.0.232`. |
| Standard TCP/IP Port | Windows printer port that sends jobs directly to a printer IP address. |
| Port name | Windows label for the printer connection. It is often generated automatically from the IP. |
| Printer properties | Windows settings for port, driver, configuration, accounting and test page. |
| Accounting / User ID | Optional Fuji Xerox setting used to identify or authorize print jobs. |
| Test page | A Windows-generated page used to confirm the driver and printer connection work. |

## Important correction about the remembered value `133`

The value `133` is probably **not the printer IP name**.

A likely interpretation is:

```text
Printer properties
→ Configuration
→ Accounting
→ User ID / password
```

FUJIFILM printer drivers can have an Accounting section where a device-registered user ID and password are entered.

This matches the memory of entering something like `133` plus a password in printer properties. However, this is still only a likely explanation. Confirm it in Gino's manual or with Gino before entering anything.

Do not store the actual password in this vault.

## Likely complete workflow

### Step 1: confirm network and admin access

Before installation:

- connect the laptop to the company network
- confirm the employee can access the MIS 公用 folder
- use an administrator account if Windows asks for installation permission

### Step 2: choose the correct driver folder

For the 27F printer:

```text
27F_事務機_FujiXerox ApeosPort-VI C5571_192.168.0.232_win
```

For the 30F printer:

```text
30F_事務機_FujiXerox ApeosPort-VI C3370_192.168.0.233_win_x64
```

### Step 3: copy installer folder locally

Copy the correct folder from the MIS network share to the employee laptop first.

Reason:

- installer may need local admin permission
- running from a network share can be slower or blocked
- local copy is easier to retry

### Step 4: run the correct installer

For C5571:

```text
run launcher.exe
```

For C3370:

```text
run setup.exe
```

Follow the internal manual when the installer asks for model, connection type, IP address or port.

### Step 5: check whether Windows created the correct TCP/IP port

Windows 11 path:

```text
Settings
→ Bluetooth & devices
→ Printers & scanners
→ select the printer
→ Printer properties
→ Ports
```

Check that the selected port points to the correct printer IP:

```text
C5571 → 192.168.0.232
C3370 → 192.168.0.233
```

If the installer did not create the port, the normal manual method is:

```text
Add port
→ Standard TCP/IP Port
→ enter printer IP address
```

The Windows port name is normally filled automatically. It is not usually a password or employee code.

### Step 6: configure accounting/authentication if required

Possible path, depending on driver version:

```text
Printer properties
→ Configuration
→ Accounting
```

The internal manual may require:

- user ID
- department/accounting code
- password/passcode

The remembered value `133` may belong here.

Do not guess. Check Gino's manual or ask Gino.

### Step 7: print a Windows test page

Windows 11 path:

```text
Settings
→ Bluetooth & devices
→ Printers & scanners
→ select printer
→ Printer properties
→ General
→ Print Test Page
```

A successful test confirms:

- driver installed
- correct port selected
- laptop can reach printer
- accounting settings are accepted, if required

## If the printer does not appear or test page fails

### Check 1: network reachability

```powershell
ping 192.168.0.232
ping 192.168.0.233
```

A failed ping is a clue, but not absolute proof because some devices can block ping.

### Check 2: port selection

Open:

```text
Printer properties → Ports
```

Confirm the correct TCP/IP port is checked.

### Check 3: wrong driver/model

Confirm the installed driver matches:

```text
ApeosPort-VI C5571
or
ApeosPort-VI C3370
```

### Check 4: accounting/user ID

If the job enters the queue and disappears or the printer rejects it, verify the internal Accounting/User ID settings.

### Check 5: Print Spooler

If jobs remain stuck in Windows, see [[Printer Spooler]].

## Things still needing confirmation

- Exact location of 常用 IP address → IP 分配表
- Exact file name of the 手冊 inside Gino's folder
- Whether `133` is User ID, department code, accounting code or something else
- Whether each printer has a different user ID/password
- Whether installer automatically creates the TCP/IP port or it must be added manually

## Related notes

- [[Printer Spooler]]
- [[Windows Service Troubleshooting Basics]]
- [[Basic Network Commands for Support]]
- [[Company Network Big Picture]]
- [[2026-07-30]]
