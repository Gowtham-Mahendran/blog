---
title: "VSCodium"
description: "Minimal notes for installing and using VSCodium on Linux"
tags: ["development"]
draft: false
---

## Installation

Official guide: https://vscodium.com/

**Add repository key**

```bash
wget -qO - https://gitlab.com/paulcarroty/vscodium-deb-rpm-repo/raw/master/pub.gpg \
  | gpg --dearmor \
  | sudo dd of=/usr/share/keyrings/vscodium-archive-keyring.gpg
```

**Add repository**

```bash
echo 'deb [arch=amd64,arm64 signed-by=/usr/share/keyrings/vscodium-archive-keyring.gpg] https://download.vscodium.com/debs vscodium main' \
  | sudo tee /etc/apt/sources.list.d/vscodium.list
```

**Install**

```bash
sudo apt update && sudo apt install codium
```

Use `codium-insiders` instead of `codium` for the insiders build.

**Launch**

```bash
codium
```
