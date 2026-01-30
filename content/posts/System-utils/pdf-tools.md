---
title: "PDF tools"
description: "Minimal notes for common PDF operations on Linux"
tags: ["system utilities"]
draft: false
---

## xpdf-utils / poppler-utils

Install (Debian replaces `xpdf-utils` with `poppler-utils`):

```bash
sudo aptitude install xpdf-utils
```

Decrypt PDF and create PostScript:

```bash
pdftops -upw YOURPASSWORD-HERE input.pdf
```

Creates `input.ps`.

Convert PostScript back to PDF (no password):

```bash
ps2pdf input.ps
```

## qpdf

Decrypt a restricted PDF:

```bash
qpdf --decrypt restricted-input.pdf unrestricted-output.pdf
```

## pdftk

Install:

```bash
sudo aptitude install pdftk
```

### Add / edit PDF bookmarks (outline)

Export metadata:

```bash
pdftk book.pdf dump_data > meta.txt
```

Add bookmarks at the end of `meta.txt`:

```text
BookmarkBegin
BookmarkTitle: Chapter 1 Introduction
BookmarkLevel: 1
BookmarkPageNumber: 5
```

Subsections must follow parent level:

```text
BookmarkBegin
BookmarkTitle: 3.1 Line Parameters
BookmarkLevel: 2
BookmarkPageNumber: 85
```

Write updated outline back to PDF:

```bash
pdftk book.pdf update_info meta.txt output book_with_outline.pdf
```
### PDF security

To scan a PDF for suspicious indicators, use `pdfid.py` (Didier Stevens Suite):

Reference: https://github.com/DidierStevens/DidierStevensSuite/blob/master/pdfid.py

```bash
python3 pdfid.py file.pdf
````
