**Signal IPTV — Downloads**

Installers for **Signal IPTV**, a desktop IPTV player for macOS and Windows.
This repo hosts builds only — there is no source code here.

**Which file to download**

Go to [**Releases**](../../releases/latest) and grab the file for your machine:

| Platform | File |
|---|---|
| Apple Silicon (M1/M2/M3/M4) | `Signal-IPTV-x.y.z-arm64.dmg` |
| Intel Mac | `Signal-IPTV-x.y.z.dmg` |
| Windows | `Signal-IPTV-Setup-x.y.z.exe` |

**Installing on macOS**

1. Open the `.dmg` and drag **Signal IPTV** into **Applications**.
2. Launch it from Applications (not from the mounted disk image).

**"Apple could not verify this app is free of malware"**

This build is not signed with a paid Apple Developer ID, so Gatekeeper shows
a warning the first time you open it. This is expected — here's how to get
past it:

1. Click **Done** on the warning dialog.
2. Open **System Settings → Privacy & Security**, scroll to the bottom, and
   click **Open Anyway** next to the mention of Signal IPTV.
3. Launch the app again and click **Open Anyway** on the second prompt.
   macOS remembers this choice permanently after that.

If the app is blocked outright or quits immediately on launch, clear the
quarantine flag and re-sign it locally from Terminal:

```bash
xattr -cr "/Applications/Signal IPTV.app"
codesign --force --deep --sign - "/Applications/Signal IPTV.app"
```

**Installing on Windows**

1. Run `Signal-IPTV-Setup-x.y.z.exe`.
2. Choose an install location (or accept the default) and finish the wizard.

**"Windows protected your PC" (SmartScreen)**

This build is not signed with a paid code-signing certificate, so
Windows SmartScreen flags it as unrecognized. To proceed:

1. On the blue SmartScreen dialog, click **More info**.
2. Click **Run anyway**.

If SmartScreen or your antivirus removed/quarantined the downloaded file
instead of just warning, restore it from quarantine in Windows Security
(**Windows Security → Virus & threat protection → Protection history**)
before trying the steps above.

**Updates**

New versions are published here as new Releases. This app does not
auto-update from this repo — check back here (or watch this repo's
Releases) for new versions.
