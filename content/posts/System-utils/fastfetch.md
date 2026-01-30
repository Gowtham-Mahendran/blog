---
title: "Fastfetch"
description: "Notes on using Fastfetch for system information and terminal startup"
tags: ["system utilities"]
draft: false
---

## Install

Download Fastfetch from GitHub:  
https://github.com/fastfetch-cli/fastfetch

Install the `.deb` package.

## Usage

Run Fastfetch:

```bash
fastfetch
```

Use a specific distro logo:

```bash
fastfetch --logo debian
```

Show all information:

```bash
fastfetch -c all.jsonc
```

Query a specific module in JSON format:

```bash
fastfetch -s <module> --format json
```

## Modules

Replace `<module>` with one of the supported modules (CPU, GPU, Memory, Disk, OS, Kernel, Network, etc.).
Full list is available in the Fastfetch repository documentation.

## Auto-run on terminal start

Edit bash configuration:

```bash
nano ~/.bashrc
```

Add at the end:

```bash
fastfetch
```

Fastfetch will now run whenever a new terminal is opened.

