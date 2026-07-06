# IE Mode and Legacy Systems

tags: #internship #troubleshooting #edge #ie-mode #legacy-system

## When this applies

Use this when an old internal system behaves strangely in Microsoft Edge, especially if it originally depended on Internet Explorer.

Common symptoms:

- page cannot open
- login fails
- button does nothing
- report/export fails
- popup opens but feature does not work
- works on one PC but not another

## Quick mental model

Some old systems are built for Internet Explorer behavior. Edge can emulate that through IE Mode, but only for configured URLs. If the exact URL, protocol, or popup page is not included, part of the system may open in normal Edge mode and fail.

## Important rule from 2026-07-02

- IE Mode should only be used for YINXUN / 音訊.
- Other old internal web pages may not need IE Mode.
- Some older pages should be opened through the internal local host/address instead.
- Compatibility mode also needs to be enabled when required.

## Checklist

1. Confirm exact issue:
   - cannot open?
   - login failed?
   - button failed?
   - report failed?
2. Confirm scope:
   - only this PC?
   - everyone?
3. Confirm network:
   - `nslookup`
   - `Test-NetConnection`
4. Confirm exact URL:
   - `http`
   - `https`
5. Confirm whether this system should use IE Mode:
   - YINXUN / 音訊: yes, based on current notes
   - other old pages: do not assume; check first
6. Check IE Mode:
   - look for IE icon near the address bar
7. Check compatibility mode if the system requires it.
8. Check Edge IE settings:
   - `edge://settings/defaultBrowser`
9. Check IE diagnostics:
   - `edge://compat/iediagnostic`
10. Try safe fixes:
   - restart Edge
   - use the exact saved URL
   - re-add the IE Mode entry
   - allow popup windows
   - clear cookies/site data for the affected site if re-adding does not work
11. If there is a password prompt, ask the user/senior instead of assuming the password.
12. If still failing, escalate with clear information.

## Specific notes from internship

### 音訊 / YINXUN system

Possible causes:

- IE Mode / Edge mode mismatch
- popup window opens after clicking a feature, but popup is normal Edge mode
- URL was saved as `https`, but the system needs `http`
- compatibility mode is not enabled
- cookies/site data are stale or broken
- wrong account/password for the specific PT machine or counter

Specific checklist:

- [[YINXUN IE Mode and Login Checklist]]

Important login rule:

- PT01 and PT02 do not necessarily use the same password.
- If a password prompt appears, ask the user or senior.
- Do not store passwords in this vault.

Check near the URL bar for IE-mode status or settings.

## Escalation info to collect

- PC/user affected
- exact URL used
- screenshot of error
- whether it works on another PC
- whether problem affects everyone or only one person
- what was already tried
- whether password prompt appears

## Related daily logs

- [[2026-06-24]]
- [[2026-07-01]]
- [[2026-07-02]]
- [[2026-07-06]]
