# Omnoku

Downloads for **Omnoku**, a variant Sudoku app for Linux, Windows and Android.

This repository holds **binaries only**: no source code, no build workflows. Every release is
published from a private build and kept indefinitely. Use the issue tracker here for downloads,
installs and the app itself; there is no source to read or patch.

## Download

- **[Latest release](https://github.com/M4ss1ck/omnoku/releases/latest)** — pick the file for your
  device.
- **[omnoku.massick.dev](https://omnoku.massick.dev)** — play in the browser, or let the site pick
  the right installer for you.

| Platform | File | Notes |
| --- | --- | --- |
| Linux x86_64 | `.AppImage` | `chmod +x` it and run it. Works on most distributions. |
| Linux x86_64 | `.deb` | Debian, Ubuntu and derivatives. |
| Linux x86_64 | `.rpm` | Fedora, openSUSE and derivatives. |
| Windows x86_64 | `.exe` (NSIS) | See the SmartScreen note below. |
| Android arm64-v8a | `.apk` | Almost every phone made since 2017. |
| Android x86_64 | `.apk` | Emulators and x86 Chromebooks. |

macOS and Google Play are not available.

## Windows SmartScreen

The Windows installer is **not** signed with a paid code-signing certificate, so Windows
SmartScreen will show "Windows protected your PC" the first time you run it. This is expected: it
means the file has no purchased certificate, not that anything is wrong with it. To continue,
click **More info**, then **Run anyway**. Verify the checksum first if you want to be sure the
download is intact (see below).

## Android

Install the APK **over** your existing Omnoku app. Do not uninstall first — uninstalling deletes
your local progress. Your browser will ask for permission to install unknown apps the first time;
that permission is for the browser, not for Omnoku.

Pick `arm64-v8a` unless you know you are on an x86_64 device.

## Verifying your download

Every release ships a `SHA256SUMS` file listing the hash of each installer. Compare it with the
file you downloaded:

```sh
# Linux / macOS
sha256sum --check --ignore-missing SHA256SUMS
```

```powershell
# Windows PowerShell, then compare the hash with the one in SHA256SUMS
Get-FileHash .\Omnoku_*_x64-setup.exe -Algorithm SHA256
```

Checksums prove the download is not corrupted or truncated. They do not prove who published it —
for that, download only from this repository's releases page or from
[omnoku.massick.dev](https://omnoku.massick.dev).

## Release catalog

Each release also carries a `release.json` describing every installer in it. The app and the site
read it to tell you when a newer version exists. Omnoku never installs an update by itself: it
tells you, you download, you install.

`withdrawn.json` in this repository lists versions that were withdrawn and the newer version that
replaces each one. A withdrawn release is superseded, never deleted; an already installed copy
keeps working until you replace it.

## Support

- **Something wrong with a download or an install?**
  [Open an issue](https://github.com/M4ss1ck/omnoku/issues).
- **Questions about the app itself?** Same place.

## Terms

See [LICENSE](./LICENSE). Omnoku is proprietary software; you may download, install and run it,
and you may not redistribute or reverse engineer it.
