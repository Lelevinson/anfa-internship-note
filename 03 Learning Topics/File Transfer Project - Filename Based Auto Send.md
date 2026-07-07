# File Transfer Project - Filename Based Auto Send

tags: #internship #project #file-transfer #backend #feature-request

## Source

Feature request from Alex / manager.

Related daily note:

- [[2026-07-06]]

## Main requirement

The project should avoid making users manually select files one by one.

Instead, the system should use the file name to decide how/where to send the file.

Reason:

```text
If users still need to choose/upload files manually,
it is not very different from uploading files one by one on a website.
```

## Current idea

The app watches or reads a folder, then:

```text
find file
→ read file name
→ parse meaning from file name
→ decide destination/type
→ send file to backend/server
→ record success/failure
```

## What "from file name" probably means

The file name may contain useful information, such as:

- patient/customer code, if allowed by company policy
- department/system code
- file type/category
- date/time
- target destination
- task type

Example only:

```text
TYPE_DEPARTMENT_DATE_ID.ext
```

Do not assume the real naming rule. Confirm with Alex/mentor.

## Possible modules

```text
main/controller
reader
filename_parser
router/decision
backend_client
logger
```

### reader

Finds files from a source folder.

Responsibilities:

- check folder exists
- list files
- filter valid file types
- avoid temporary/incomplete files

### filename_parser

Reads the file name and extracts meaning.

Responsibilities:

- split file name by agreed rule
- validate file name format
- return structured info

Example output idea:

```text
file_path
file_type
department
date
target
```

### router / decision

Uses parsed file-name info to decide what to do.

Responsibilities:

- decide which backend endpoint or destination to use
- decide if the file should be skipped
- report unclear file names

### backend_client

Sends the file to the backend/server.

Responsibilities:

- choose method/protocol
- send file
- include token/auth if required
- handle backend response
- retry or log failure

### logger

Records what happened.

Responsibilities:

- file sent successfully
- file failed
- reason failed
- timestamp
- backend response if useful

## Backend connection question

The next stage needs connection to company backend.

Need to decide:

```text
How should this app send files to the server?
```

Possible methods:

| Method | Meaning | Notes |
|---|---|---|
| HTTP API upload | App sends file to backend endpoint | Common for web/backend integration |
| FTP/SFTP | App copies file to server folder | Common for file transfer, but ask company standard |
| Shared folder/NAS copy | App copies file to network folder | Simple, but permission/path handling matters |
| Database record + file storage | App uploads file and backend records metadata | More structured, needs backend design |

Do not decide alone. Confirm with Alex/mentor/backend owner.

## If using HTTP API

Likely pattern:

```text
POST /upload
Content-Type: multipart/form-data
file = actual file
metadata = parsed info from file name
```

Questions:

- What is the API endpoint?
- Is the method `POST`?
- Does it need token/authentication?
- Should metadata come from file name, request body, or both?
- What response means success?
- What should happen if upload fails?

## Important design point

This feature is not only "copy file" anymore.

It becomes:

```text
automatic file detection
+ filename rule validation
+ routing/decision logic
+ backend communication
+ logging/error handling
```

## Questions to ask Alex/mentor

- What is the exact file-name format?
- Which part of the file name decides destination/type?
- What file types should be handled?
- Where is the source folder?
- Should the app watch continuously or run manually?
- What backend/server should receive the files?
- Should the app send by HTTP API, FTP/SFTP, or shared folder?
- Is token/auth required?
- What should happen to files after successful send?
- What should happen to files that fail validation?

## Related notes

- [[File Transfer Project]]
- [[FTP Service]]
- [[Basic Network Commands for Support]]
- [[Company Network Big Picture]]
