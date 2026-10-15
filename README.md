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

Releases are numbered **MAJOR.MINOR.PATCH** and written short, the way early Minecraft did it:

- **2.0** is a revamp
- **1.5** adds something new
- **1.4.1** fixes or tweaks something

The full rules are in [VERSIONING.md](VERSIONING.md). Releases up to 0.5.113 came before
these rules and are listed in the [changelog](CHANGELOG.md).

## License

Proprietary. Copyright © 2025-2026 BXC. All rights reserved. See [LICENSE](LICENSE).
