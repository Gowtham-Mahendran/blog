---
title: "Oh My Zsh essentials"
description: "Notes on installing Oh My Zsh, themes, and useful plugins"
tags: ["productivity"]
date: 2026-02-17
draft: false
---

## Install

Check if Zsh is installed:

```bash
zsh --version
```

If not:

```bash
sudo apt install zsh
```

Install **Oh My Zsh** (official repo):
[https://github.com/ohmyzsh/ohmyzsh](https://github.com/ohmyzsh/ohmyzsh)

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

After installation, create a new KDE Konsole profile and set the command to:

```text
/bin/zsh
```

## Themes

Edit `.zshrc`:

```bash
nano ~/.zshrc
```

Set theme:

```bash
ZSH_THEME="agnoster"
```

Theme list:
[https://github.com/ohmyzsh/ohmyzsh/wiki/Themes](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

Optional: add `fastfetch` at the end of `.zshrc` to show system info on startup.

## Zsh navigation features

* `Desktop` → same as `cd Desktop`
* `/home/user/Desktop` → direct path jump
* `..` → one directory up
* `...` → two directories up
* Tab completion expands paths (e.g. `/h/g/De` → `/home/gowtham/Desktop`)

## Plugins

Edit plugins in `.zshrc`:

```bash
plugins=(git docker-compose web-search)
```

Reload:

```bash
source ~/.zshrc
```

### docker-compose

Plugin shortcuts:
[https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/docker-compose](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/docker-compose)

Example:

```bash
dcup
```

### web-search

Search from terminal:

```bash
brs uni oldenburg
```

Open URLs directly:

```bash
open amazon.de
```
