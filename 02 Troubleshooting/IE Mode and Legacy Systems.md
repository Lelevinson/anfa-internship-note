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
5. Confirm IE Mode:
   - look for IE icon near the address bar
6. Check Edge IE settings:
   - `edge://settings/defaultBrowser`
7. Check IE diagnostics:
   - `edge://compat/iediagnostic`
8. Try safe fixes:
   - restart Edge
   - use the exact saved URL
   - re-add the IE Mode entry
   - allow popup windows
9. If still failing, escalate with clear information.

## Specific notes from internship

### 音訊 system

Possible causes:

- IE Mode / Edge mode mismatch
- popup window opens after clicking a feature, but popup is normal Edge mode
- URL was saved as `https`, but the system needs `http`

Check near the URL bar for IE-mode status or settings.

## Escalation info to collect

- PC/user affected
- exact URL used
- screenshot of error
- whether it works on another PC
- whether problem affects everyone or only one person
- what was already tried

## Related daily logs

- [[2026-06-24]]
- [[2026-07-01]]
