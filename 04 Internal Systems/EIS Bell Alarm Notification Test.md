# EIS Bell Alarm Notification Test

tags: #internship #internal-system #eis #dashboard #notification #testing

## Purpose

Test whether the bell/alarm notification behavior is the same between the EIS dashboard and another dashboard/system.

This is planned as a 3-day test.

## Systems involved

Known:

- EIS dashboard
- new system / 新系統
- appointment dashboard / 預約 dashboard

Need to confirm:

- the second dashboard/system to compare with EIS

## Tentative testing flow

Current understanding:

```text
新系統 / new system
→ 預約 dashboard / appointment dashboard
→ choose 報到
→ press bell/alarm
→ check whether notification appears
→ compare result on EIS dashboard and other dashboard/system
```

## Important flow detail

The user may need to select **報到** first from the appointment dashboard before pressing the bell/alarm.

Do not test only by pressing the bell directly unless Gino confirms that is valid.

## Ask Gino to confirm

Need to ask Gino for the correct flow.

Questions:

- What is the exact correct testing flow?
- Which dashboard/system should be compared with EIS?
- What does the bell/alarm button represent?
- Is 報到 always required before pressing the bell?
- Where should the notification appear?
- How long should the notification take to appear?
- What should be recorded if it does not appear?

## Test matrix

| Date | Dashboard/system | 報到 selected first? | Bell pressed? | Notification appeared? | Same as EIS? | Notes |
|---|---|---|---|---|---|---|
| Day 1 | EIS |  |  |  |  |  |
| Day 1 | Other dashboard |  |  |  |  |  |
| Day 2 | EIS |  |  |  |  |  |
| Day 2 | Other dashboard |  |  |  |  |  |
| Day 3 | EIS |  |  |  |  |  |
| Day 3 | Other dashboard |  |  |  |  |  |

## What to record

- date/time
- tester
- dashboard/system
- test patient/case if safe to record, otherwise use generic label
- whether 報到 was selected
- whether bell/alarm was pressed
- whether notification appeared
- where notification appeared
- whether EIS and the other dashboard behaved the same
- screenshot only if it does not include sensitive personal data

## Related notes

- [[2026-07-07]]
- [[Appointment and Registration Notes]]
- [[Systems Glossary]]
