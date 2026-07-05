# Event Viewer Reading Guide

tags: #internship #learning #windows #event-viewer #logs

## Main idea

Event Viewer is where Windows records system and application events. It is not only for programmers. IT support uses it to understand what happened before, during, or after a problem.

## When to use it

Use Event Viewer when:

- a service starts then stops again
- Windows shows an unclear error
- an app crashes
- printing/network/login issue keeps happening
- you need evidence before asking a senior

## Where to look first

Open:

```text
Start menu → Event Viewer
```

Most useful places:

```text
Windows Logs → System
Windows Logs → Application
```

## What the levels mean

| Level | Meaning |
|---|---|
| Information | Normal event; usually not a problem |
| Warning | Something may be wrong, but system continued |
| Error | Something failed |
| Critical | Serious system-level issue |

## What to copy for escalation

When you find a relevant event, record:

- time
- level
- source
- event ID
- general message
- affected PC/user/system
- what the user was doing

## How to search by time

The fastest way is usually not searching the whole log. Instead:

1. Ask when the problem happened.
2. Open System/Application log.
3. Look around that time.
4. Compare with the time you restarted a service or reproduced the problem.

## How to avoid overthinking logs

Event Viewer always contains many warnings/errors. Do not assume every red error is related.

A useful event should match at least one of these:

- same time as problem
- same app/service name
- same device/printer/network component
- repeated every time the problem happens

## Example: service problem

If Print Spooler stops again after restarting:

1. note the exact time it stopped
2. check Windows Logs → System
3. search around that time
4. record the error/source/event ID
5. ask senior with evidence

## Related notes

- [[Windows Service Troubleshooting Basics]]
- [[Windows Services and Event Viewer]]
- [[Printer Spooler]]
- [[Windows Repair and Evidence Collection]]
