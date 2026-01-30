---
title: "Privacy browsers essentials"
description: "Notes for installing Brave Browser and Tor on Linux"
tags: ["networking"]
draft: false
---

## Brave Browser

Linux download page:  
https://brave.com/linux/

Install:

```bash
sudo aptitude install curl
curl -fsS https://dl.brave.com/install.sh | sh
```

## Tor

Install Tor service:

```bash
sudo aptitude install tor
```

Install Tor Browser (GUI):

```bash
flatpak install flathub org.torproject.torbrowser-launcher
```
