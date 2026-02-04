---
title: "Publish to PyPI with uv"
description: "Minimal commands to build and publish a Python package using uv"
date: 2026-02-04
tags: ["development"]
draft: false
---

## Build

```bash
uv build
```

## Publish to TestPyPI

```bash
uv publish --token pypi-xxxx --publish-url https://test.pypi.org/legacy/
```

## Publish to PyPI

```bash
uv publish --token pypi-xxxx
```

Add this **Advice** section—short and practical:


## Advice

**Clean build artifacts before building**
```bash
  rm -rf dist/
```

**Bump version before publishing**

  * Update `version` in `pyproject.toml`
  * PyPI does **not** allow re-uploading the same version
  * Always use **test-pypi** before uploading to **PyPI**

**Update `CHANGELOG.md`**

  * Clearly list added/changed/fixed items for the release

**Set correct development status**

  * Update `classifiers` in `pyproject.toml`

    * `Development Status :: 3 - Alpha`
    * `Development Status :: 4 - Beta`
    * `Development Status :: 5 - Production/Stable`

