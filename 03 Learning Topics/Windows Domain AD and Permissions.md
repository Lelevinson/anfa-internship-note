# Windows Domain AD and Permissions

tags: #internship #learning #windows #domain #ad #permissions

## Why this matters

Company computers often use Windows domain accounts and Active Directory. Access to internal systems, shared folders, NAS, and databases may depend on network connection and account permission.

## Simple mental model

```text
Your PC joins company domain
→ you log in with company account
→ AD checks who you are
→ permissions decide what you can access
```

## Terms

- AD / Active Directory: company directory for users, computers, and permissions.
- Domain: managed company network identity system.
- Permission / 權限: access right to a file, folder, database, system, or feature.
- NAS: network storage, often used for shared files.

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

## Related notes

- [[2026-06-16]]
- [[Systems Glossary]]
