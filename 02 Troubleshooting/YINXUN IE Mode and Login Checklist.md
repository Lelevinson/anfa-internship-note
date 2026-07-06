# YINXUN IE Mode and Login Checklist

tags: #internship #troubleshooting #yinxun #ie-mode #edge #login

## When this applies

Use this when YINXUN / 音訊 cannot open, opens in the wrong browser mode, or prompts for account/password.

## Main idea

YINXUN is a legacy internal system. The problem may be:

```text
IE Mode setting
HTTP vs HTTPS URL
old/stale IE Mode entry
cookies/site data
account/password for the specific PT machine/user
```

Do not assume it is only a browser problem or only a password problem.

## Usual troubleshooting order

### 1. Check Edge default browser / IE Mode settings

Open:

```text
edge://settings/defaultBrowser
```

Check whether the YINXUN URL is already added to IE Mode.

Look for:

- Internet Explorer compatibility section
- allowed/reloaded IE Mode pages
- whether the exact YINXUN URL is listed

### 2. Check `http` vs `https`

YINXUN may require the exact protocol.

Check carefully:

```text
http://...
https://...
```

If the saved URL uses the wrong protocol, the site may fail or open incorrectly.

### 3. Re-add the IE Mode entry

If it cannot open even though it looks configured, remove/re-add or re-save the IE Mode page entry.

Reason:

- old setting may not apply
- URL may not match exactly
- protocol may be wrong
- Edge may need the entry refreshed

### 4. Clear cookies/site data

If re-adding still does not work, clear cookies/site data for the YINXUN site.

Reason:

- old login/session cookie may be broken
- stale site data may keep redirecting incorrectly
- previous login state may conflict

Be careful not to clear all browser data unless needed. Prefer clearing only the site/system data if possible.

### 5. If password prompt appears, ask the user

YINXUN access may require account/password.

Important rule:

```text
Do not assume every PT machine/account uses the same password.
```

Current note:

- PT01 and PT02 do not necessarily use the same password.
- The counter / 櫃檯 case was PT02, so it used a different password.
- If anything prompts for password, ask the user or senior.
- Do not store passwords in this vault.

## Quick checklist

```text
1. Is this YINXUN? If yes, IE Mode likely needed.
2. Open edge://settings/defaultBrowser.
3. Check whether YINXUN is in IE Mode list.
4. Check exact URL: http or https.
5. Re-add/re-save IE Mode entry if needed.
6. Restart/reload Edge.
7. Clear YINXUN cookies/site data if still failing.
8. If password prompt appears, ask user/senior.
9. Do not store password.
```

## What to record if still failing

- PC/location, for example PT01 or PT02 if known
- user/counter affected
- exact URL, without sensitive tokens
- whether URL is HTTP or HTTPS
- whether IE Mode icon appears
- screenshot of error
- whether cookies/site data were cleared
- whether another PT machine works
- whether password prompt appears

## Related notes

- [[IE Mode and Legacy Systems]]
- [[Internal System Access Rules]]
- [[Company Network Big Picture]]
- [[2026-07-06]]
