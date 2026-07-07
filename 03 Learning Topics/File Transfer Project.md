# File Transfer Project

tags: #internship #project #python #file-transfer

## Current design idea

The project can be split into separate responsibilities:

```text
main/controller
reader
transfer
```

After Alex's new feature request, the design may need more parts:

```text
main/controller
reader
filename_parser
router/decision
backend_client
logger
```

See [[File Transfer Project - Filename Based Auto Send]].

## Module responsibilities

### main / controller

Coordinates the program flow.

Possible responsibilities:

- receive high-level input
- call reader
- call filename parser
- call router/decision logic
- call transfer/backend client
- show final result

### reader

Handles file-path reading.

Possible responsibilities:

- receive source path
- validate path exists
- list files
- return file list to controller
- filter only valid files

### filename_parser

New possible responsibility from Alex's request.

Purpose:

- read file name
- understand what the file is for
- extract useful information
- validate whether file name follows the agreed rule

This helps avoid manual file picking/uploading.

### router / decision

New possible responsibility from Alex's request.

Purpose:

- decide where/how to send the file based on file name
- decide whether to skip invalid files
- decide which backend endpoint or method to use

### transfer / backend_client

Handles file movement or backend sending logic.

Possible responsibilities:

- receive file list or one file
- validate target path/server/API
- send/copy/upload files
- include token/auth if needed
- confirm success/failure
- log backend response

## 2026-07-01 note: token / 驗證

Need to clarify what token and validation mean in this project:

- user identity?
- transfer permission?
- file integrity?
- API access?
- simple confirmation code?

## 2026-07-06 note: Alex feature request

Alex/manager requested an additional feature:

- avoid making users manually choose files one by one
- use the file name to decide where/how to send the file
- otherwise it feels too similar to normal manual website upload
- next part needs backend connection
- need to decide which method/protocol/API style sends the file to the server

See [[File Transfer Project - Filename Based Auto Send]].

## Questions to ask

- Where should validation happen?
- Should reader only read, or also validate?
- Should transfer know about token logic?
- Is token required before listing files or before transferring files?
- What is the exact file-name format?
- What backend/server should receive the files?
- Should files be sent through HTTP API, FTP/SFTP, or shared folder/NAS?
- If HTTP API is used, what endpoint and method should be used?
- What should happen after successful send?
- What should happen if file name is invalid or upload fails?

## Related daily logs

- [[2026-06-30]]
- [[2026-07-01]]
- [[2026-07-06]]
