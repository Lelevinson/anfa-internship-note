# File Copy and Permission Issues

tags: #internship #troubleshooting #windows #files #permissions #network-drive

## When this applies

Use this when a user cannot copy a file, open a network folder, or access a shared location.

This connects to notes about database files, NAS/shared folders, and the DICOM copy problem.

## Main idea

A file-copy problem is usually one of these:

```text
Path problem
Permission problem
Network problem
File is locked/in use
Storage/full/format problem
Application-specific rule
```

## First questions

Ask/check:

- What file is being copied?
- From where to where?
- Does the source exist?
- Does the target folder exist?
- Is it local disk, USB, NAS, or shared network path?
- Is the error about permission, path not found, file in use, or disk space?
- Does it happen only for this user or everyone?

## Basic checks

### 1. Confirm path

Check both source and target paths.

Common issue:

- mapped drive exists on one PC but not another
- shortcut points to an old location
- user typed path differently

### 2. Confirm network

If it is a network folder:

- confirm PC is on the company network
- check whether other internal systems are reachable
- check whether another PC can access the same folder

### 3. Confirm permission

Permission issue clues:

- Access denied
- You do not have permission
- login prompt appears
- works for senior account but not user account

Do not guess credentials. Record the exact path and ask who manages permission.

### 4. Confirm file lock

File may be open by another user/application.

Clues:

- file is in use
- cannot overwrite
- copy works after closing related program

### 5. Confirm target storage

Check:

- target disk full?
- USB/storage connected?
- target is read-only?
- file name too long?

## What to collect before escalating

- source path
- destination path
- exact error message
- screenshot
- user/account affected
- PC name if available
- whether other users can copy the same file
- whether other files can be copied to the same target

## Internship-related notes

- Some access may require company network first.
- Some file/database access may require permission approval.
- DICOM copy issue should be treated as a file path/permission/network/system-specific problem until confirmed.

## Related notes

- [[Windows Domain AD and Permissions]]
- [[Internal System Access Rules]]
- [[General IT Support Triage]]
- [[Systems Glossary]]
- [[2026-06-16]]
- [[2026-06-24]]
