# BlueQuery

A desktop client for **PostgreSQL** and **Amazon RDS for PostgreSQL** on macOS.

- Saved connections, with passwords kept in the macOS Keychain
- Database navigator with table sizes
- SQL editor with suggestions, table aliases, formatting, and errors pointed out at the exact line
- Table view you can filter (with suggestions) and edit, plus a one-row view for reading a single record
- SQL bookmarks, and export or import of connections (passwords encrypted with a passphrase)
- Updates itself when a new version is released

This repository holds only the release files. The source code lives in
[ace53thntu/bluequery](https://github.com/ace53thntu/bluequery).

## Requirements

- macOS 11 (Big Sur) or later
- A Mac with Apple Silicon (M1 or later)

## Install

**Quickest:** open Terminal and run

```shell
curl -fsSL https://github.com/ace53thntu/bluequery-releases/releases/latest/download/install.sh | sh
```

This installs the latest version into Applications. Before installing, it checks that the download
matches the release's checksum, that the app is BlueQuery at the announced version, and that its code
signature is valid.

**Or download the installer:**
[BlueQuery-darwin-arm64.dmg](https://github.com/ace53thntu/bluequery-releases/releases/latest/download/BlueQuery-darwin-arm64.dmg).
Open it and drag BlueQuery into Applications.

BlueQuery isn't notarized by Apple. The first time you open the version from the .dmg, macOS blocks it.
To open it, go to **System Settings → Privacy & Security** and click **Open Anyway**. The Terminal
install above doesn't hit this block.

## Updates

From version 1.1.0 on, BlueQuery checks for a new version 30 seconds after it starts, then every
4 hours. When one is out, a bar appears with:

- **Update now**: downloads the new version, checks it, then asks you to restart
- **Later**: installs it the next time you quit BlueQuery
- **Skip this version**: the automatic check stops offering that version

**Help → Check for updates…** checks right away. You can turn the automatic check off in **Help → About**.

Every update is signed. BlueQuery refuses a download unless its signature, checksum, version and
developer all match. Your connections, saved passwords and bookmarks are kept across updates.

If you have version 1.0.0, install the latest version once with the Terminal line or the .dmg. From then
on, it updates itself.

## Where BlueQuery keeps your data

- Connections, bookmarks and settings: `~/Library/Application Support/BlueQuery/`
- Saved passwords: the macOS Keychain, under **BlueQuery**

## Uninstall

1. Quit BlueQuery and delete it from Applications.
2. To remove your data too, delete `~/Library/Application Support/BlueQuery/`.
3. Open **Keychain Access** and delete the item named **BlueQuery**.

## Release files

Each release has these files:

| File | What it's for |
|---|---|
| `BlueQuery-<version>-darwin-arm64.dmg` | Installer for that version |
| `BlueQuery-darwin-arm64.dmg` | The same installer under a name that never changes, for a fixed download link |
| `install.sh` | The one-line installer |
| `BlueQuery-<version>-darwin-arm64.zip`, `bluequery-update.json` | Used by the app's automatic updater |

What changed in each version is in its [release notes](https://github.com/ace53thntu/bluequery-releases/releases).

## License

BlueQuery is released under the MIT License. It includes open-source libraries and fonts; their licences
ship with the app (**Help → Third-party licences**) and with each .dmg.

BlueQuery is an independent tool. It isn't affiliated with the PostgreSQL Global Development Group or
Amazon Web Services.
