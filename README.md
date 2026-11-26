# Budget: downloads

This repository holds the **installers** for Budget, an offline budgeting and forecasting app for your desktop. Your data stays on your computer, encrypted, and the app works fully offline. The only time it goes online is an optional check for today's mortgage rates, which is off unless you turn it on in **Settings → Privacy**. That check sends none of your data. Nothing personal ever leaves your computer.

The app's source code isn't here. These repos only publish releases.

> **Website:** [budget.esaith.com](https://budget.esaith.com) · **Support:** [admin@esaith.com](mailto:admin@esaith.com)

---

## Download

Budget is published in two channels, each in its own repository:

| Channel | Where | What it is |
| --- | --- | --- |
| **Stable** | [esaith/budget-stable › Releases](https://github.com/esaith/budget-stable/releases/latest) | Tested releases. Most people want this one. |
| **Alpha** | [esaith/budget-alpha › Releases](https://github.com/esaith/budget-alpha/releases) | Early test builds for alpha testers, marked **Pre-release**. Versions look like `1.0.4-alpha.1`. |

Open the newest release and download the file for your computer from **Assets**:

| Your computer | File | Stable | Alpha |
| --- | --- | --- | --- |
| Windows 10 / 11 (64-bit) | `.exe` installer | ✅ | ✅ |
| Linux (64-bit, x64) | `.deb` (Ubuntu, Debian, Linux Mint) | Coming soon | ✅ |
| Linux (64-bit, x64) | `.AppImage` (most other distributions) | Coming soon | ✅ |
| macOS | | Coming later | Coming later |

There's no `.rpm` (Fedora) or ARM build yet.

> [!NOTE]
> GitHub also lists **Source code (zip)** and **Source code (tar.gz)** on every release. Those are added automatically and only contain this README. You don't need them.

---

## Install on Windows

1. Run the `.exe` you downloaded.
2. The installer isn't code-signed yet, so Windows may show **"Windows protected your PC."** Click **More info**, then **Run anyway**.
3. Follow the installer's steps, then open **Budget** from the Start menu.

## Install on Linux

**`.deb` (Ubuntu, Debian, Linux Mint)**

```bash
sudo apt install ./<the-file-you-downloaded>.deb
```

Budget then appears in your app menu under **Office** (or **Finance**), and you can start it from a terminal with `budget`.

**`.AppImage` (other distributions)**

```bash
chmod +x <the-file-you-downloaded>.AppImage
./<the-file-you-downloaded>.AppImage
```

If it won't start on a newer Ubuntu, install FUSE 2: `sudo apt install libfuse2t64` (on Ubuntu 22.04 the package is `libfuse2`).

> [!IMPORTANT]
> **Encryption on Linux needs a keyring.** Budget keeps its encryption key in your desktop's keyring (GNOME Keyring or KWallet), the way most Linux desktops already work. On a system with no keyring, a new install **stays unencrypted**, and data that was already encrypted asks for your recovery key at every start. **Settings → Encryption** shows which one you have.

## First start

The setup guide walks you through your accounts. You can also choose **Try it with demo data** to look around with a made-up household first.

### Updating

Download the new version and install it over the old one. **Your data is kept.** There's no automatic update yet, so check Releases for new versions.

### Uninstalling

Uninstalling removes the app but **leaves your data folder in place**, so reinstalling picks up where you left off. Your data lives here, and **Settings → About** shows the exact folder:

| System | Data folder |
| --- | --- |
| Windows | `%APPDATA%\budget` |
| Linux | `~/.config/budget` |

---

## Check the download (optional)

Every release lists SHA-256 checksums and includes `.sha256` files. To confirm your download wasn't damaged or altered:

**Windows (PowerShell), in the folder you downloaded to:**

```powershell
Get-FileHash .\<the-file-you-downloaded>.exe
```

The `Hash` it prints should match the one in the release notes, ignoring upper and lower case.

**Linux, with the `.sha256` file in the same folder:**

```bash
sha256sum -c <the-file-you-downloaded>.sha256
```

It should say `OK`.

---

## Alpha testers: please read

> [!IMPORTANT]
> This is early software. Take these steps to protect your data:
>
> - **Save your recovery key on day one.** The setup guide asks you to. Without it, a backup can't be restored on a different computer.
> - **Keep backups somewhere else.** In **Settings → Backups**, choose a folder such as OneDrive or a USB drive.
> - **Not ready to trust it with real numbers?** Use the demo data.

### Reporting a problem

Email **[admin@esaith.com](mailto:admin@esaith.com)** with:

- the **version**, from **Settings → About**, and whether you're on Windows or Linux (and which distribution)
- what you did, what you expected, and what happened
- a report from **Settings → Troubleshooting → Save a report**, if you can

The report contains settings and logs, not your transactions. Please don't send screenshots that show real account numbers.

---

## Release notes

Each release's notes list what changed. Inside the app, **Settings → About → What's new** shows the same changes.

---

## License

Budget is proprietary software. © 2026 eSaith. All rights reserved.

You may download and install the releases here for your own use under the terms shown on [budget.esaith.com](https://budget.esaith.com). The open-source components the app uses are listed in **Settings → About → Open-source licenses**.
