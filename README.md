<p align="center">
  <img src="assets/icon.png" width="96" alt="Parallax">
</p>

<h1 align="center">Parallax</h1>

<p align="center">
  Point of sale, inventory, purchasing, production and accounting for a multi-branch business.
</p>

<p align="center">
  <a href="https://github.com/jackthereaper2006/parallax-releases/releases/latest"><b>Download the latest release</b></a>
  &nbsp;·&nbsp;
  <a href="CHANGELOG.md">Changelog</a>
  &nbsp;·&nbsp;
  <a href="VERSIONING.md">Versioning</a>
</p>

---

This repository hosts the installers and update feed for Parallax. The source code is private.

## Download

Open the [latest release](https://github.com/jackthereaper2006/parallax-releases/releases/latest)
and pick the file for your system.

| System | File | Updates itself |
|---|---|---|
| Windows 10 / 11 (64-bit) | `Parallax-Setup-<version>.exe` | Yes |
| Linux (x86-64), any distribution | `Parallax-<version>-x86_64.AppImage` | Yes |
| Debian / Ubuntu | `Parallax-<version>-amd64.deb` | No |
| Linux, portable | `Parallax-<version>-x64.tar.gz` | No |

The `.yml` and `.blockmap` files are read by the updater. You do not need to download them.

## Install

**Windows.** Run the installer and follow the steps. Parallax installs for all users of the
PC and adds a desktop shortcut.

**Linux (AppImage).**

```sh
chmod +x Parallax-*-x86_64.AppImage
./Parallax-*-x86_64.AppImage
```

**Debian / Ubuntu.**

```sh
sudo apt install ./Parallax-*-amd64.deb
```

The `.deb` and `.tar.gz` builds do not update themselves. Install a newer file by hand, or use
the AppImage.

## Updates

Parallax checks for a new version in the background and downloads it quietly. It installs the
next time Parallax is closed.

In a shop with several machines, HQ updates first and the tills follow. From HQ, the owner can
push a new version to every machine at once with **Settings ▸ Application ▸ Force update all machines**.

A release that changes the database says so under **Before you update** in its notes. Back up
HQ before installing one of those.

## Versions

Every release has three numbers, **MAJOR.MINOR.PATCH**. The biggest change in a release
decides which one goes up:

| Number | Goes up when the release… | Example |
|---|---|---|
| Patch | fixes or tweaks something that already exists | 1.4 → 1.4.1 |
| Minor | adds something new, or changes the database | 1.4 → 1.5 |
| Major | redesigns the app in a way everyone notices | 1.9 → 2.0 |

The numbers to the right of the one that goes up start again from zero, so 1.4.3 is followed
by 1.5. No number stops at 9: 1.9 is followed by 1.10. A version ending in `.0` is shown
without it, so 1.5.0 appears in the app and on this page as **Parallax 1.5**.

The full rules are in [VERSIONING.md](VERSIONING.md). Releases up to 0.5.113 came before
these rules and are listed in the [changelog](CHANGELOG.md).

## License

Proprietary. Copyright © 2025-2026 Muhammad Waqas Butt. All rights reserved. Copying, modifying or reverse engineering Parallax is not permitted. See [LICENSE](LICENSE).
