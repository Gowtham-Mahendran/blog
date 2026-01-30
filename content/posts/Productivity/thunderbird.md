---
title: "Thunderbird"
description: "Minimal notes for installing Thunderbird and setting up Exchange + signature"
tags: ["productivity"]
draft: false
---

## Installation

Install from the Debian repository:

```bash
sudo aptitude install thunderbird
```

## HTML signature

Minimal HTML signature template:

```html
<div style="font-family: Arial, sans-serif; font-size: 12px; color: #333; line-height: 1.4;">
  <p style="margin: 0; font-weight: bold;">Best Regards,</p>
  <p style="margin: 0; font-weight: bold;">Gowtham Mahendran</p>
  <p style="margin: 0;">MSc Sustainable Renewable Energy Technologies</p>
  <p style="margin: 0;">University of Oldenburg, Germany</p>
  <p style="margin: 0;">
    <a href="https://linkedin.com/in/gowtham-mahendran" style="color: #1a73e8; text-decoration: none;">LinkedIn</a> |
    <a href="https://github.com/Gowtham-Mahendran" style="color: #1a73e8; text-decoration: none;">GitHub</a>
  </p>
</div>
```

## Exchange calendar

**Install extensions:**

1. **TbSync**
2. **Provider for Exchange ActiveSync**

**Steps:**

* Open **TbSync Account Manager**
* Add an Exchange account using credentials
* Sync calendar

The calendar will appear in Thunderbird.

