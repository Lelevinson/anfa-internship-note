# Raw Internship Log: 2026-06-15 to 2026-07-01

tags: #internship #raw-note

This file preserves the original mixed-language notes. Cleaned versions are split into daily logs, troubleshooting notes, learning topics, and internal-system notes.

## Legend

- `Q` = question to ask
- `N` = note / learning topic
- `S` = solution / troubleshooting
- `T` = task / thing to try
- `Problem` = unresolved issue

---

## 2026-06-15

- [ ] Q: own personal company account
- [ ] Q: login for MS Edge
- [ ] N: using Docker for environment
- [ ] N: learn about Docker for PHP, DB, Apache, etc.
- [ ] N: try Gino's whole WSL setup, and check `/project` folder
- [ ] N: belajar multi architecture or sth, complex PHP (getting real)
- [ ] N: 客戶資料 buat lihat customer (table, personal card), tambahin user, banyak data-data penyakit juga
- [ ] N: CodeIgniter, Laravel, PHP, MVC

## 2026-06-16

- [ ] N: internal webmail URL noted separately
- [ ] N: system properties → computer name/domain changes
- [ ] S: klo konek database file2, hrs konek ethernet/wifi dlu sm perlu di apply quanxian ke Alex, cek2 doc
- [ ] N: AD server
- [ ] N: cari info ANFA-NAS
- [ ] N: dengji note:
  1. cek yg pasangan ada nanya dokter, sm ada ruangan, cek biandang, klo ada contoh 3, ada 1 pair, sm ada gak pair. jd gk usah input 1 lg.
  2. cek tanggal
  3. klo cuma 1 gk pair, terus ERP, gantiin aja, pilih qita xiangmu
  4. ada jg yg cuma reserve kamar, gk ad dokter, itu pilih dokter gk usah pilih
- [ ] N: counter problem

## 2026-06-18

- [ ] N: DataTables, Select2, Datepicker, Bootstrap framework; check explanation
- [ ] S: iPad YouTube not playing: 輸入來源 → HDMI 4, because blocked by AirPlay
- [ ] N: appointment doctor selection notes:
  - If 月 no. 6: doctor choose 706
  - If 月 10 and 12 doctor 營養師: choose their names in room
  - If 月 Taichung doctor: choose 134
  - If 1 day: choose full day
- [ ] N: `pv` for running SQL in Ubuntu, because running SQL script in GUI can lag a lot
- [ ] N: must set database on Ubuntu SQL to allow other connections
- [ ] N: memory management in PHP
- [ ] N: OOP buat kode lu
- [ ] N: things to learn: 高併發
- [ ] S: minta password → `sfc /scan now`; if not possible, record complete info: photo + problem + etc.
- [ ] S: printer problem → Print Spooler from Windows service / AnyDesk service → stop → check if can print
- [ ] S: Zoom meeting → login
- [ ] N: cara pake new system
- [ ] N: pake framework buat kode
- [ ] S: tablet/laptop cannot connect to Wi-Fi or AnyDesk because it may be too old

## 2026-06-24

- [ ] S: TV dashboard: check top-right area for EIS or 音訊
- [ ] N: bug in 護理部 → 預約管理: daily appointment sorting after crossing time
- [ ] N: interface/code should use OOP concepts: inheritance, polymorphism. Learn more tools that have not been used before.
- [ ] S: 音訊 issue may be from IE/Edge mode. Maybe a popup window opens after clicking a feature, but the popup is in Edge mode. Check near URL bar if setting is on/off.
- [ ] S: besides IE mode in 音訊, possible HTTPS issue. If URL was saved before, save again using only `http` mode.
- [ ] S: `erp.anfa.com.tw` Wi-Fi keeps reloading, especially rooms 703/705: change laptop.
- [ ] N: FTP service
- [ ] Problem: 藥師 user DICOM file cannot copy
- [ ] T: cari server simulator, belajar merge seperti switch Wi-Fi

## 2026-06-26

- [ ] S: 會議室 already HDMI2 but cannot share screen:
  - unplug rear HDMI first
  - change HDMI option first, e.g. to HDMI 3
  - plug antenna/controller into user's device
  - plug rear HDMI again
  - should work after that
- [ ] S: printer problem: Windows Services → Print Spooler → Stop → Start
- [ ] N: Windows Services and Event Viewer

## 2026-06-30

- [x] explained to Alex: file transfer project module split:
  - main/controller
  - reader: receive path, validate, return list of files
  - transfer: receive list of files, validate, transfer from source to target, confirm
- [ ] S: meeting room schedule conflict, want to change from Zoom → ask Alex → login Zoom and change time. Do not enter meeting room directly. If no password, ask.
- [ ] S: 會議室 wireless controller does not need to be plugged into the main machine; should be plugged into the laptop.

## 2026-07-01

- [ ] File transfer project: token, 驗證
- [ ] S: IE Mode: use `edge://compat/iediagnostic` to check IE-mode-related things
- [ ] S: IE mode checklist:
  1. Confirm exact issue: cannot open, login fail, button fail, report fail?
  2. Confirm scope: only this PC or everyone?
  3. Confirm network: `nslookup` / `Test-NetConnection`
  4. Confirm exact URL: `http` vs `https`
  5. Confirm IE mode: look for IE icon
  6. Check Edge IE setting: `edge://settings/defaultBrowser`
  7. Check diagnostics: `edge://compat/iediagnostic`
  8. Try safe fixes: restart Edge, exact URL, re-add IE mode, allow popup
  9. If still failing, escalate with good info
- [ ] S: AP problem: try `netsh wlan show interfaces`
