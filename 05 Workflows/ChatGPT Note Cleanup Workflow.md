# ChatGPT Note Cleanup Workflow

tags: #internship #workflow #chatgpt #obsidian

## Purpose

Use this note to keep the workflow simple. You do not need to explain the whole repo every time.

## Short prompt to use

```text
Clean this into my internship repo:
[paste raw note]
```

If the note belongs to a specific day:

```text
Add this to today's internship notes:
[paste raw note]
```

## What ChatGPT should do

For each raw note:

1. Preserve the raw note in `00 Raw/`.
2. Add or update the correct file in `01 Daily Logs/`.
3. Create/update reusable notes if the information is useful later.
4. Link related notes using Obsidian links.
5. Add glossary terms if new Chinese/internal terms appear.
6. Avoid adding passwords or private customer data.

## Cleanup rules

Keep both versions:

- raw wording: useful because it preserves what was heard quickly
- cleaned wording: useful because it is easier to search/read later

## Expansion rule for learning notes

When expanding notes, do not only write "check, record, report". Add practical explanation too:

- explain the main concept first
- explain confusing terms
- give concrete low-risk fixes when possible
- separate safe intern actions from admin/senior actions
- include Windows settings paths when useful
- include commands and what their outputs mean
- include decision trees for problems with many possible causes

Example: for Wi-Fi/AP issues, include terms like AP, SSID, DHCP, DNS, gateway, adapter, signal, and also include actions like forgetting a network, renewing IP, flushing DNS, disabling/enabling adapter, and when not to touch AP settings.

## Good reusable-note categories

- troubleshooting fix
- internal-system workflow
- equipment location
- learning topic
- question to ask mentor/senior
- glossary term

## After ChatGPT updates GitHub

On phone:

```text
GitSync → pull/sync → open Obsidian
```

On PC:

```text
Obsidian Git plugin or GitHub Desktop → pull → open Obsidian
```
