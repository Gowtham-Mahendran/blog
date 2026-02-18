---
title: "Debian 13"
description: "Replacing Windows with Debian 13: BIOS setup, repositories, and base tooling"
tags: ["system utilities"]
date: 2025-03-05
draft: false
---

This note documents replacing Windows with **Debian 13 (Trixie)** on an HP laptop, including BIOS setup, offline install, and post-install configuration.

## 1. Booting Debian

### Create bootable USB

Download the **firmware-included ISO** from:  
https://www.debian.org/distrib/  
Example: `debian-13.1.0-amd64-DVD-1.iso`

Create USB using **Rufus** (https://rufus.ie):
- Partition scheme: **GPT**
- Target system: **UEFI (non-CSM)**

### BIOS / UEFI (HP)

- Reboot → press `F10` → BIOS
- Security → Secure Boot Configuration → **Disable Secure Boot**
- Reboot → press `F9`
- Select `UEFI: <USB device>`

### Install Debian

- Choose **Graphical Install**
- Skip network drivers if not detected
- Use **Guided partitioning**
- Set **root password**
- Create normal user

### Display manager

If multiple desktops are installed:
- `gdm3` → GNOME
- `sddm` → KDE Plasma

### Post-install basics

Switch to root:
```bash
su -
````

Update system:

```bash
apt update
apt upgrade
```

Add user to sudo:

```bash
usermod -aG sudo <username>
```

Verify:

```bash
groups <username>
```

## 2. Debian package sources

Edit sources list:

```bash
sudo nano /etc/apt/sources.list
```

Add:

```bash
deb http://deb.debian.org/debian trixie main contrib non-free non-free-firmware
deb http://security.debian.org/debian-security trixie-security main contrib non-free non-free-firmware
deb http://deb.debian.org/debian trixie-updates main contrib non-free non-free-firmware
deb http://deb.debian.org/debian trixie-backports main contrib non-free non-free-firmware
```

Update:

```bash
sudo apt update
apt list --upgradable
sudo apt upgrade
```

## 3. Package management

### Aptitude

Preferred package manager:

```bash
sudo apt install aptitude
```

Usage:

* `/` search
* `+` select
* `g` install

### Curl

```bash
sudo aptitude install curl
```

### Flatpak

```bash
sudo apt install flatpak
```

Add Flathub:

```bash
flatpak remote-add --if-not-exists flathub https://dl.flathub.org/repo/flathub.flatpakrepo
```

Reboot after setup.
