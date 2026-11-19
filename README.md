# Hesabo Releases

Signed update manifests and installers for **Hesabo** (حسابو), a private,
offline-first personal finance app.

> This repository contains **release artifacts only** — the signed update
> manifest (`version.json`) and, under [Releases](../../releases), the Android
> APKs and the Windows installer. **No application source code lives here.**
> The source is maintained in a separate private repository.

## What is here

| File | Purpose |
| --- | --- |
| `version.json` | The signed update manifest the app reads on startup. |
| Releases → `vX.Y.Z` | The Android split APKs and the Windows installer for that version. |

## How the updater trusts this

- `version.json` is signed with **Ed25519**. The app embeds only the public
  key and verifies the signature over canonical JSON before acting on it.
- Every asset URL is **HTTPS**. Each asset carries an exact `size` and
  `sha256`; the app re-checks both after download and refuses a mismatch.
- Android APKs are signed with the long-lived Hesabo release certificate, so
  an update can only replace an installation signed by the same key.
- The Windows installer is a per-user Inno Setup package; it never touches
  user data, and the app makes a database safety copy before running it.

If you are not the Hesabo app, you do not need to do anything with this
repository.

## برای کاربران فارسی‌زبان

این مخزن فقط فایل‌های انتشار برنامه‌ی «حسابو» را نگه می‌دارد: فایل امضاشده‌ی
`version.json` و فایل‌های نصب در بخش Releases. کد منبع برنامه اینجا نیست.
به‌روزرسانی داخل برنامه به‌صورت خودکار و امن از همین فایل‌ها انجام می‌شود؛
امضای دیجیتال و SHA-256 هر فایل پیش از نصب بررسی می‌شود.

---

Maintained by AION Industries. Issues with the app itself should be reported
through the app's support channel, not this repository.
