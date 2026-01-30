---
title: "UV Astral"
description: "Concise notes on uv for Python environment and project management"
tags: ["development"]
draft: false
---

## Install

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
````

Documentation: [https://docs.astral.sh/uv/](https://docs.astral.sh/uv/)

## Virtual environments

| Purpose                         | Command                         |
| ------------------------------- | ------------------------------- |
| Create venv with Python version | `uv venv .venv --python 3.12.0` |

## Dependency management

| Purpose                 | Command               |
| ----------------------- | --------------------- |
| Generate lock file      | `uv lock`             |
| Sync dependencies       | `uv sync`             |
| Sync with extras        | `uv sync --extra dev` |
| List installed packages | `uv pip list`         |

## Python versions

| Purpose                          | Command                            |
| -------------------------------- | ---------------------------------- |
| Install Python versions          | `uv python install 3.12 3.13 3.14` |
| Pin Python version               | `uv python pin 3.12`               |
| List installed Pythons           | `uv python list --only-installed`  |
| Find system Python (ignore venv) | `uv python find --system`          |

## Ruff

| Purpose     | Command               |
| ----------- | --------------------- |
| Lint code   | `uv run ruff check .` |
| Format code | `uv run ruff format`  |

## Pytest

| Purpose              | Command            |
| -------------------- | ------------------ |
| Run tests            | `uv run pytest`    |
| Quiet mode           | `uv run pytest -q` |
| Show stdout / prints | `uv run pytest -s` |

