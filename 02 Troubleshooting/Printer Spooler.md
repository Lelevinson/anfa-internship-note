# Printer Spooler

tags: #internship #troubleshooting #windows #printer

## When this applies

Use this when a Windows PC cannot print, print jobs are stuck, or the printer behaves normally but the PC still cannot send jobs.

## First fix to try

1. Open **Windows Services**.
2. Find **Print Spooler**.
3. Stop the service.
4. Start the service again.
5. Test printing.

## Why this works

The Print Spooler is the Windows service that queues print jobs. If the queue/service is stuck, restarting it can clear the stuck state without changing the printer itself.

## If still failing

Collect:

- printer name/model
- PC/user affected
- whether other PCs can print
- screenshot/error message
- whether jobs appear in print queue
- what was already tried

## Related daily logs

- [[2026-06-18]]
- [[2026-06-26]]
