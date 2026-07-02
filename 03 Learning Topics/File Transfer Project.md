# File Transfer Project

tags: #internship #project #python #file-transfer

## Current design idea

The project can be split into separate responsibilities:

```text
main/controller
reader
transfer
```

## Module responsibilities

### main / controller

Coordinates the program flow.

Possible responsibilities:

- receive high-level input
- call reader
- call transfer
- show final result

### reader

Handles file-path reading.

Possible responsibilities:

- receive source path
- validate path exists
- list files
- return file list to controller

### transfer

Handles file movement logic.

Possible responsibilities:

- receive file list
- validate target path
- copy/transfer files
- confirm success/failure

## 2026-07-01 note: token / 驗證

Need to clarify what token and validation mean in this project:

- user identity?
- transfer permission?
- file integrity?
- API access?
- simple confirmation code?

## Questions to ask

- Where should validation happen?
- Should reader only read, or also validate?
- Should transfer know about token logic?
- Is token required before listing files or before transferring files?

## Related daily logs

- [[2026-06-30]]
- [[2026-07-01]]
