---
title: "GlobalProtect VPN"
description: "Minimal notes for installing and using GlobalProtect via openconnect"
tags: ["networking"]
draft: false
---

## Installation

Install the **GlobalProtect-openconnect** `.deb` package from:  
https://github.com/yuezk/GlobalProtect-openconnect

**Verify**

```bash
gpclient --version
```

**Connect**

Use `sudo` and authenticate when prompted.

```bash
sudo gpclient connect <gateway>
```
