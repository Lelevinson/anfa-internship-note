# ANFA Internship Notes

This repository is an Obsidian-ready knowledge base for internship notes.

Start here in Obsidian:

- [[Home]]

## Main workflow

```text
You type raw notes to ChatGPT
→ ChatGPT tidies and pushes Markdown files here
→ GitSync pulls this repository to the phone
→ Obsidian opens the local GitSync folder as a vault
```

## Folder structure

```text
00 Raw/              Original messy notes, preserved for reference
01 Daily Logs/       Notes split by date
02 Troubleshooting/  Reusable IT-support checklists and fixes
03 Learning Topics/  Things to study later
04 Internal Systems/ System-specific notes and workflows
05 Workflows/        How to capture and clean notes
99 Glossary/         Chinese terms, Indonesian shorthand, unclear terms
```

## Most useful entry points

- [[Home]]
- [[General IT Support Triage]]
- [[Internal System Access Rules]]
- [[Learning Backlog]]
- [[Terms To Confirm]]
- [[Raw Note Capture Template]]
- [[ChatGPT Note Cleanup Workflow]]

## Safety note

Keep this repository private. Avoid storing passwords, private customer data, screenshots with personal information, sensitive medical details, or internal documents.

For company-specific systems, store general process notes and questions. Avoid storing real customer/user records.

## How to use in Obsidian

Open this repository folder as an Obsidian vault. The notes use normal Markdown links like `[[IE Mode and Legacy Systems]]` and tags like `#internship`.

## How to add new notes through ChatGPT

Use a short prompt like:

```text
Clean this into my internship repo:
[paste raw note]
```

ChatGPT should preserve the raw note, update the daily log, create reusable topic notes when useful, and link related notes.
