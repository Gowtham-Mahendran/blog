---
title: "External monitor setup (xrandr)"
description: "Notes for configuring external displays using xrandr"
tags: ["system utilities"]
draft: false
---

## External monitor (xrandr)

Preview current display setup:

```bash
xrandr
```

List available GPU output providers:

```bash
xrandr --listproviders
```

Place external monitor to the right of the laptop display:

```bash
xrandr --output HDMI-1-0 --auto --right-of eDP
```

Duplicate laptop display:

```bash
xrandr --output HDMI-1-0 --mode 1920x1080 --same-as eDP
```
