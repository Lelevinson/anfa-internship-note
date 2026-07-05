# Windows Services and Event Viewer

tags: #internship #learning #windows #services #event-viewer

## Why this matters

Many basic IT support fixes start by checking Windows Services or Event Viewer.

This is useful because a visible problem often depends on an invisible background process.

Example:

```text
Printing problem
→ maybe printer is fine
→ Windows Print Spooler service is stuck
```

## Windows Services

Windows Services are background programs managed by Windows.

Examples:

- Print Spooler
- network-related services
- update-related services
- remote-support-related services
- database/server-related services

## What to check in Services

For a service, check:

- status: running, stopped, paused
- startup type: automatic, manual, disabled
- dependencies: other services it needs
- whether it stops again after restart

Do not casually change startup type or disable services. For internship support, the safer skill is knowing what to observe, restart if approved, and report clearly.

See [[Windows Service Troubleshooting Basics]].

## Event Viewer

Event Viewer records system and application logs. It can help answer:

- when did the error happen?
- what service crashed?
- what warning/error was recorded?
- is this a system issue or application issue?

See [[Event Viewer Reading Guide]].

## First things to learn

- Open Windows Services
- Stop/start a service safely
- Find Print Spooler
- Open Event Viewer
- Check Windows Logs → System
- Check Windows Logs → Application
- Copy useful error details

## Practical workflow

```text
Something fails
→ check related service
→ restart only if safe/approved
→ test again
→ if it fails again, check Event Viewer by time
→ collect evidence and ask senior
```

## Related notes

- [[Windows Service Troubleshooting Basics]]
- [[Event Viewer Reading Guide]]
- [[Printer Spooler]]
- [[Windows Repair and Evidence Collection]]
- [[2026-06-26]]
