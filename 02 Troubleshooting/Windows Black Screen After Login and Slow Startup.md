# Windows logs in to a black screen / extremely slow startup

tags: #internship #troubleshooting #windows #black-screen #startup

## What happened

- The computer was extremely slow during startup.
- It eventually reached the Windows PIN login screen.
- After entering the PIN, the screen became dark/black and the desktop did not appear.
- `Ctrl + Alt + Delete` still worked and showed:
  - Lock / 鎖定
  - Switch user / 切換使用者
  - Sign out / 登出
  - Change password / 變更密碼
  - Task Manager / 工作管理員
- Restart was selected.
- Restarting took a long time, but after waiting, Windows eventually started normally.

## Confirmed conclusion

The confirmed solution in this incident was simply:

```text
Restart the computer
→ wait several minutes
→ log in again
```

The desktop then loaded correctly.

The exact cause was **not confirmed**.

The `explorer.exe` method below was prepared as a fallback, but it was **not needed or tested in this incident**.

## My method — what actually worked

1. Open `Ctrl + Alt + Delete`.
2. Select **Restart**.
3. Wait because Windows may take several minutes to finish restarting.
4. After the restart completed, log in normally.
5. The desktop loaded correctly.

## Alternative method — if the black screen happens again

This method was suggested but **not tested in this incident**.

If `Ctrl + Alt + Delete` still works:

1. Select **工作管理員 / Task Manager**.
2. Select **執行新工作 / Run new task**.
3. Enter:

```text
explorer.exe
```

4. Press Enter.
5. Wait around 10–30 seconds.

`explorer.exe` controls the Windows desktop, taskbar, Start menu, and File Explorer.

Starting it manually may restore the desktop if Windows logged in successfully but Windows Explorer failed to start.

This is only a possible fix. It does **not** prove that Windows Explorer caused the problem.

## If explorer.exe does not work

1. Open `Ctrl + Alt + Delete` again.
2. Try **登出 / Sign out**, then log in again.
3. **鎖定 / Lock** is unlikely to fix this because it only returns to the lock screen.
4. If Windows is completely frozen, force shutdown only as a last resort:
   - Hold the physical power button for around 10 seconds.
   - Wait around 10 seconds.
   - Turn the computer on again.

## Warning about forced shutdown

- Do not immediately cut the power while Windows is restarting.
- If Windows displays an update message such as **Working on updates** or **Do not turn off your computer**, wait longer.
- A forced shutdown may interrupt Windows or an update, so only use it when the computer is clearly stuck for a long time.

## Possible causes — not confirmed

- Windows Explorer failed to start.
- The disk, CPU, or another startup process was overloaded.
- A Windows update or background process delayed login.
- A graphics driver temporarily froze.

## Related notes

- [[Windows Repair and Evidence Collection]]
- [[Windows Services and Event Viewer]]
- [[Event Viewer Reading Guide]]
