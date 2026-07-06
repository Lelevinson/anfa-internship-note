# Company Network Big Picture

tags: #internship #learning #network #domain #server #windows

## Main idea

A company network is not just Wi-Fi. It is a managed environment where computers, users, permissions, servers, printers, shared folders, and internal websites are connected.

A simple picture:

```text
Your laptop/PC
→ company network, Wi-Fi or Ethernet
→ domain controller / AD server checks identity
→ DNS helps find internal systems
→ file servers, NAS, printers, databases, internal websites
```

## What is a domain?

A Windows domain is a managed identity system for a company.

Instead of every computer having separate local usernames, the company has a central place that manages accounts and computers.

Example idea:

```text
Local account:
This account only exists on this one PC.

Domain account:
This account exists in the company directory and can be used across company-managed resources.
```

## What is AD / Active Directory?

Active Directory, usually called AD, is the system/server that stores and manages:

- user accounts
- computer accounts
- groups
- permissions
- login rules
- sometimes policy/settings pushed to company PCs

For your internship notes, think of AD as the company identity and permission brain.

## What is a domain controller?

A domain controller is a server that runs AD services.

When you log in with a domain account, the PC needs to verify your identity with a domain controller, directly or using cached login information.

Simple flow:

```text
You type domain username/password
→ PC asks domain controller: is this valid?
→ domain controller checks AD
→ login allowed or denied
```

## Domain account vs local account

### Domain account

Looks like:

```text
ANFA\username
username@company-domain
```

Used for:

- logging in to company PC
- accessing shared folders
- accessing internal systems
- permission checks
- sometimes webmail or company apps

### Local account

Looks like:

```text
PC-NAME\username
```

Used only on that PC.

A local account usually does not automatically give access to company shared folders or internal systems.

## What does it mean when a PC joins a domain?

A domain-joined PC is registered with the company domain.

It means the company can recognize the computer, not just the user.

This matters because some access may require both:

```text
valid domain user
+
trusted/domain-joined company computer
+
correct company network
```

## How login is connected to network access

Your login proves who you are.

The network proves where you are connected from.

Permissions decide what you can access.

Example:

```text
Correct account, wrong network
→ internal system may not open

Correct network, wrong account/permission
→ system opens but access denied

Correct account and network, wrong browser mode
→ old system may still fail
```

## What is a server?

A server is a computer that provides something to other computers.

Examples in a company:

| Server type | What it provides |
|---|---|
| Domain controller | login and identity checking |
| DNS server | translates internal names to IP addresses |
| DHCP server | gives IP addresses to devices |
| File server / NAS | shared folders and documents |
| Database server | database for systems/apps |
| Web server | internal websites/systems |
| Print server | shared printers/print queues |

A server is not always a huge machine. It can be a physical server, virtual machine, or cloud/server room resource.

## What is DNS in company network?

DNS translates names to IP addresses.

Example:

```text
internal-system-name
→ DNS looks it up
→ returns IP address
→ browser connects to that IP
```

This is why an internal system may only open inside the company network: outside the network, the DNS name or IP may not be reachable.

## What is DHCP?

DHCP gives devices their network address automatically.

When your laptop connects to company Wi-Fi/Ethernet:

```text
Laptop: Can I have an IP address?
DHCP server: Use this IP, gateway, DNS settings.
```

This is why renewing IP usually does not change your domain account. IP address is network location. Domain account is identity.

See [[DHCP IP Renewal and Domain Login]].

## What is NAS / shared folder?

NAS means network-attached storage. It is storage on the network, not inside your laptop.

Example:

```text
Your laptop
→ company network
→ NAS/file server
→ shared folder
```

Access depends on:

- network connection
- account permission
- folder permission
- sometimes department/group membership

## Why permission problems happen

A permission problem may happen because AD groups control access.

Example:

```text
Alex or senior gives your account/group permission
→ AD/file server knows you are allowed
→ shared folder opens
```

Without permission, you may see:

- access denied
- login prompt
- folder does not open
- system page opens but feature is blocked

## Why company systems sometimes need IE Mode

This is separate from domain/network.

A system can fail because of browser compatibility even when network and permission are correct.

Example:

```text
Network works
Login works
Permission is okay
But old web feature still fails
→ maybe IE Mode / compatibility mode issue
```

See [[IE Mode and Legacy Systems]].

## Common troubleshooting map

When a company system does not work, think by layer:

```text
1. Device: is the laptop working?
2. Network: Wi-Fi/Ethernet connected?
3. IP/DHCP: does it have a valid IP?
4. DNS: can it find the system name?
5. Server: can it reach the system server/port?
6. Identity: logged in with correct domain account?
7. Permission: account/group allowed?
8. Browser/app: IE Mode, compatibility mode, popup, HTTP/HTTPS?
```

This prevents jumping to the wrong conclusion.

## Example: shared folder cannot open

Possible causes:

```text
not on company network
DNS cannot find server
file server unavailable
not logged in with domain account
account lacks permission
mapped drive path is wrong
```

See [[File Copy and Permission Issues]].

## Example: internal website cannot open

Possible causes:

```text
wrong Wi-Fi/network
DNS problem
server/port unreachable
wrong URL, HTTP vs HTTPS
browser/IE Mode issue
account permission issue
```

See [[Basic Network Commands for Support]] and [[IE Mode and Legacy Systems]].

## Related notes

- [[Windows Domain AD and Permissions]]
- [[DHCP IP Renewal and Domain Login]]
- [[Basic Network Commands for Support]]
- [[Internal System Access Rules]]
- [[File Copy and Permission Issues]]
- [[IE Mode and Legacy Systems]]
