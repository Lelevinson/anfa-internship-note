# Windows Domain AD and Permissions

tags: #internship #learning #windows #domain #ad #permissions

## Why this matters

Company computers often use Windows domain accounts and Active Directory. Access to internal systems, shared folders, NAS, printers, and databases may depend on network connection, domain login, computer trust, and account permission.

Start with [[Company Network Big Picture]] if the whole concept feels unclear.

## Simple mental model

```text
Your PC joins company domain
→ you log in with company account
→ AD checks who you are
→ groups/permissions decide what you can access
→ servers allow or deny access
```

## Domain, AD, and server: how they connect

A company domain is a managed identity environment.

Active Directory, or AD, is the system that stores the domain's users, computers, groups, and permissions.

A server provides something to users or computers.

Example:

```text
Domain controller server
→ checks login/account identity

File server / NAS
→ stores shared folders

Database server
→ stores system data

Web server
→ hosts internal websites
```

So when you log in with a domain account, you are not logging into every server directly. You are proving your identity through the domain, then other servers can use that identity to decide access.

## Domain account vs local account

### Domain account

Common forms:

```text
ANFA\username
username@company-domain
```

Used for company-managed access:

- login to company PC
- shared folders / NAS
- internal systems
- printers
- database/file permissions

### Local account

Common form:

```text
PC-NAME\username
```

Only exists on one PC. It usually does not automatically give company network permissions.

## What does domain-joined mean?

A domain-joined PC is registered with the company domain.

This matters because some systems trust only:

```text
valid company user
+
trusted company computer
+
correct company network
```

If one of those is missing, access can fail.

## Login vs network vs permission

These are related but not the same:

| Thing | Meaning | Example failure |
|---|---|---|
| Login/account | Who you are | wrong password, wrong account |
| Network | Where you are connected | not on company Wi-Fi/Ethernet |
| DNS/server reachability | Can the PC find/reach the system | internal site name does not resolve |
| Permission | What you are allowed to access | access denied to folder/system |
| Browser/app compatibility | Whether the app can run correctly | old system needs IE Mode |

## Why you can log in but still cannot access something

Possible reasons:

- you are logged in, but not on the correct network
- the PC is not domain-joined/trusted
- your account lacks permission
- DNS cannot find the internal server
- server is reachable but feature is blocked by permission
- browser mode is wrong, such as IE Mode needed

## Why permissions may need Alex/senior

Permissions are usually managed centrally, often through AD groups or server/folder access rules.

You usually cannot fix this by guessing another password.

Better flow:

```text
identify exact folder/system
record user/account affected
record error message
check whether another user can access
ask responsible senior to grant/check permission
```

## Internship notes

- Check System Properties → Computer Name / Domain changes.
- To access database-related files, connect to the correct network first.
- Permission may need to be requested from Alex.
- Learn about AD server and ANFA-NAS.

## Things to ask / confirm

- Which account should be used for each internal system?
- Which access requires wired network vs Wi-Fi?
- Who approves permissions?
- Which shared folders are on NAS?
- Which systems require domain-joined company PCs?
- Which systems only require browser login?

## Related notes

- [[Company Network Big Picture]]
- [[DHCP IP Renewal and Domain Login]]
- [[File Copy and Permission Issues]]
- [[Internal System Access Rules]]
- [[2026-06-16]]
- [[Systems Glossary]]
