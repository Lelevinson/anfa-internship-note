# Printer Spooler

tags: #internship #troubleshooting #windows #printer #services

## When this applies

Use this when a Windows PC cannot print, print jobs are stuck, or the printer behaves normally but the PC still cannot send jobs.

## Main idea

The printer itself is not always the problem.

Windows has a background service called **Print Spooler**. It queues print jobs and sends them to the printer. If the queue/service is stuck, printing can fail even when the printer is powered on and network-connected.

## Common symptoms

- print job stuck in queue
- user clicks print but nothing happens
- printer works for other PCs but not this PC
- old print jobs keep blocking new print jobs
- restarting printer does not fix the PC

## First fix to try

1. Open **Windows Services**.
2. Find **Print Spooler**.
3. Stop the service.
4. Start the service again.
5. Test printing.

## Why this works

Restarting Print Spooler clears the stuck service state. It does not change the printer itself. It only restarts the Windows background service responsible for handling print jobs.

## If the problem comes back

Check:

- Does the Print Spooler stop again by itself?
- Is one specific document stuck?
- Does printing fail only from one application?
- Can other PCs print to the same printer?
- Can this PC print to a different printer?

If the service starts then stops again, check [[Event Viewer Reading Guide]].

## Be careful

Do not immediately delete printer drivers or change printer settings. Start with low-risk checks:

```text
Restart Print Spooler
→ test print
→ check queue
→ compare with another PC
→ collect evidence
```

If someone suggests clearing spooler files manually, ask mentor/senior first. That can require admin permission and may affect queued jobs.

## If still failing

Collect:

- printer name/model
- PC/user affected
- whether other PCs can print
- screenshot/error message
- whether jobs appear in print queue
- whether Print Spooler stays running
- what was already tried

## Related notes

- [[Windows Service Troubleshooting Basics]]
- [[Windows Services and Event Viewer]]
- [[Event Viewer Reading Guide]]
- [[General IT Support Triage]]
- [[2026-06-18]]
- [[2026-06-26]]
