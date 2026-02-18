---
title: "Networking utilities"
description: "Notes for using Proxychains and checking IP information on Linux"
tags: ["networking"]
date: 2025-11-12
draft: false
---

## Proxychains

Install:

```bash
sudo aptitude install proxychains
```

Run applications through proxychains:

```bash
sudo proxychains <browser-name>
```

## IP address

Using NetworkManager:

```bash
nmcli device show
```

Using hostname:

```bash
hostname -I
```

Using iproute2:

```bash
ip addr show
```