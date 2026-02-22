---
title: "Git"
description: "Concise notes on Git user configuration and GitHub authentication"
date: 2025-12-03
lastmod: 2026-02-22
tags: ["development"]
draft: false
---

## Configuration

| Purpose | Command |
|-------|--------|
| Show all config | `git config --list` |
| Show user name | `git config --get user.name` |
| Show user email | `git config --get user.email` |
| Set global name | `git config --global user.name "Your Name"` |
| Set global email | `git config --global user.email "you@example.com"` |
| Set local name | `git config user.name "Your Name"` |
| Unset global email | `git config --global --unset user.email` |
| Check working tree status | `git status` |


## Remotes & Authentication

GitHub no longer allows password-based authentication. Use a Personal Access Token (PAT).

`Profile > Settings > Developer settings > PAT > Fine-grained tokens`

**Required permissions:** Read access to metadata, Read and Write access to code

| Purpose | Command |
|-------|--------|
| Clone a project | `git clone <project-url>` |
| List remotes | `git remote -v` |
| Update remote (HTTPS + PAT) | `git remote set-url origin https://<user>:<PAT>@github.com/<user>/<repo>.git` |
| Switch to SSH | `git remote set-url origin git@github.com:<user>/<repo>.git` |

### GPG keys

| Purpose | Command |
|-------|--------|
| Install GNUPG | `sudo apt install gnupg`   |
| Generate key (RSA and RSA)| `gpg --full-generate-key` |
| View the keys | `gpg --list-secret-keys --keyid-format=long` |
| Export the Public Key | `gpg --armor --export <gpg-key-id>` |
| Set key to repo | `git config user.signingkey <gpg-key-id>` |
| Sign commits | `git config commit.gpgsign true` |
| Sign tags | `git config tag.gpgsign true` |

After viewing the keys, `sec rsa4096/xxxxxxxxxxxxxxxx` the **x part** is the **gpg-key-id**. The long exported public key is pasted in **Github → Settings → SSH and GPG Keys**. Once done, go to `git config list` and verify.

## Branches

| Purpose | Command |
|-------|--------|
| List local branches | `git branch` |
| List remote branches | `git branch -r` |
| Push branch to origin | `git push origin <branch>` |
| Pull branch from origin | `git pull origin <branch>` |

## Commits

| Purpose | Command |
|-------|--------|
| Add files | `git add <filename>` |
| Add multiple files  | `git add .` |
| Commit with message | `git commit -m "message"` |
| Commit and close issue [Keywords](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue)| `git commit -m "message (closes #issue)"` |
| Commit & close multiple issues | `git commit -m "message (closes #issue, closes #issue)"` |
| Verify commit author | `git log --pretty=full` |

### Commitizen

For a standardized way to commit messages and bump versions, use [commitizen](https://commitizen-tools.github.io/commitizen/).

| Purpose | Command |
|-------|--------|
| Initialize commitizen | `cz init` |
| Commit | `cz commit` |
| Release a version (auto decides based on commits)| `cz bump` |
| Release a patch   | `cz bump --increment patch` |
| Release a minor   | `cz bump --increment minor` |
| Pre-release a version | `cz bump --prerelease rc` |
| Push branch + annotated tags on pushed commits | `git push origin <branch> --follow-tags` |
| Push branch + all local tags | `git push origin <branch> --tags` |
| Push branch + specific tag(s) | `git push origin <branch> v0.0.0` |

## Cleanup

| Purpose | Command |
|-------|--------|
| Prune deleted remote branches | `git fetch -p` |
| Delete local branch | `git branch -D <branch>` |
| Delete multiple branches | `git branch -D <b1> <b2> <b3>` |

## Transfer

Transfer an existing project from Gitlab to Github. Clone the existing repo locally. Create a new clean Github repo. On the Gitlab project,

| Purpose | Command |
|-------|--------|
| Add Github url | `git remote add <url>` |
| Push to Github | `git push github --all` |


<!-- Merge and rebase needs to be added -->