# Git/GitHub Complete Guide

**A guide to understanding Git by meaning - until git push is no longer scary**

---

## Introduction

When you start programming, you'll inevitably encounter **Git** and **GitHub**.
However, for beginners, terms like:

- Repository?
- Push?
- Clone?
- What's happening with this red error message?

can feel like hitting a wall of jargon right away.

Especially your first `git push` (upload) is **the biggest hurdle, yet also the most rewarding moment**.

This guide focuses on **"the meaning of commands"** and **"why they're in that order"** to explain everything from Git/GitHub basics to advanced topics.

---

## Table of Contents

- [Concept: Understanding by Meaning](#concept-understanding-by-meaning)
- [Quick Start](#quick-start)
- [Detailed Documentation](#detailed-documentation)
- [Learning Path](#learning-path)
- [Resources](#resources)

---

## Concept: Understanding by Meaning

### Local vs Remote - The Most Important Concept

90% of GitHub confusion comes from not understanding the difference between "local" and "remote".

| Type | Location | Characteristics |
|------|----------|-----------------|
| **Local Repository** | On your PC | Not visible to anyone yet. Everything up to `git commit` happens here |
| **Remote Repository** | On GitHub | Visible to others. Only reflected after `git push` |

### The 3 Most Common Operations

| Command | Direction | Analogy |
|---------|-----------|---------|
| `git push` | Local → GitHub | Storing your desk work into a vault |
| `git pull` | GitHub → Local | Bringing the latest vault contents to your desk |
| `git clone` | GitHub → Local (first time) | Copying the entire vault to your desk |

### Learn Commands Through RPG Analogies - Never Forget Them

| Command | RPG Analogy |
|---------|-------------|
| `git init` | Create an adventure log book |
| `git add` | Select items to save |
| `git commit` | Record at a save point |
| `git remote add` | Register the save server |
| `git push` | Save to the cloud |

---

## Quick Start

### 1. Prepare Your GitHub Account

1. Create an account at [GitHub](https://github.com)
2. **Enable Two-Factor Authentication (2FA)** (password + phone authentication)

> Essential for beginners. It's easier to set up at the start than later.

### 2. Initial Git Configuration

```bash
# Set your username
git config --global user.name "Your Name"

# Set your email
git config --global user.email "your.email@example.com"

# Verify settings
git config --list
```

### 3. Push to GitHub from Scratch

If you're new, just focus on this section first.

#### Step 1: Create a "box (repository)" on GitHub

1. Click "+" at top right of GitHub → **New repository**
2. Enter Repository name
3. **Do NOT check README** (Important: An empty box causes fewer errors)
4. Click **Create repository**

#### Step 2: Execute commands on your PC

```bash
# 1. Start Git management (create adventure log)
git init

# 2. Select all files (pack your bags)
git add .

# 3. Save (confirm history)
git commit -m "First commit"

# 4. Set branch name to main
git branch -M main

# 5. Register destination (GitHub)
git remote add origin https://github.com/YOUR_ID/REPO_NAME.git

# 6. First shipment (the exciting moment!)
git push -u origin main
```

**If your code appears on GitHub, you've succeeded!**

### 4. Push to an Existing Repository

```bash
# Check first
git status
git remote -v

# Send
git add .
git commit -m "Your changes"
git push -u origin main
```

### 5. Common Beginner Errors and Solutions

```
! [rejected] main -> main (fetch first)
```

**Cause**: GitHub has a README or other files, causing history mismatch with your PC

**Solution**:
```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

---

## Detailed Documentation

### Basics
| Document | Description |
|----------|-------------|
| [Git Basic Commands](./docs/git-commands.md) | Basic commands for Windows/Mac |
| [Complete Push to GitHub Guide](./docs/push-to-github-guide.md) | Detailed 7 scenarios |
| [Terminal/Command Prompt Basics](./docs/terminal-basics.md) | CLI operation basics |
| [Shortcut Keys](./docs/shortcuts.md) | Windows/Mac/VSCode |

### GitHub
| Document | Description |
|----------|-------------|
| [GitHub Menu Complete Guide](./docs/github-ui-guide.md) | All menus and UI explained |
| [How to Use GitHub](./docs/github-usage.md) | Account creation to initial setup |
| [Repository Management](./docs/repository-management.md) | Creating and configuring repos |
| [Issues & Projects](./docs/issues-projects.md) | Project management |
| [Pull Request & Code Review](./docs/pull-request-guide.md) | Key to team development |

### AI Development Tools Integration
| Document | Description |
|----------|-------------|
| [AI Tools Integration Guide](./docs/ai-tools-integration.md) | Claude Code, Cursor, GitHub CLI |

### Practical
| Document | Description |
|----------|-------------|
| [Practical Workflows](./docs/workflow-examples.md) | Real-world workflows |
| [Branching Strategies](./docs/branching-strategies.md) | Git Flow, GitHub Flow |
| [GitHub Actions Introduction](./docs/github-actions.md) | CI/CD setup |
| [Troubleshooting](./docs/troubleshooting.md) | Common problems and solutions |
| [Hands-on Exercises](./docs/hands-on-exercises.md) | Practical exercises |

### Cheat Sheets
| Document | Description |
|----------|-------------|
| [Git Commands Cheat Sheet](./cheatsheets/git-commands-cheatsheet.md) | Command reference |
| [GitHub Shortcuts Cheat Sheet](./cheatsheets/github-shortcuts-cheatsheet.md) | Shortcut reference |

---

## Top 10 Most Used Commands

| Command | Description |
|---------|-------------|
| `git status` | Check current state |
| `git add .` | Stage all changes |
| `git commit -m "message"` | Commit changes |
| `git push` | Push to remote |
| `git pull` | Get latest from remote |
| `git branch` | List branches |
| `git checkout -b <branch>` | Create and switch to new branch |
| `git merge <branch>` | Merge branch |
| `git log` | Show commit history |
| `git diff` | Show changes |

---

## Learning Path

### For Beginners
1. Practice the [Quick Start](#quick-start) in this README
2. Learn basics with [Git Basic Commands](./docs/git-commands.md)
3. Build "push success experiences" with empty folders repeatedly

### For Intermediate Users
1. Learn [Branching Strategies](./docs/branching-strategies.md)
2. Learn collaboration with [Pull Request & Code Review](./docs/pull-request-guide.md)
3. Experience real workflows with [Practical Workflows](./docs/workflow-examples.md)

### For Advanced Users
1. Build CI/CD with [GitHub Actions](./docs/github-actions.md)
2. Optimize with [AI Tools Integration Guide](./docs/ai-tools-integration.md)
3. Contribute to open source projects

---

## Summary: Just Remember This

GitHub is about **syncing between Local (PC) and Remote (GitHub)**.

The basics are just these 3 commands:

```bash
git add .
git commit -m "memo"
git push
```

**Fastest path to mastery**: Build "push success experiences" repeatedly with empty folders.

---

## Resources

### Official Documentation
- [Git Official Documentation](https://git-scm.com/doc)
- [GitHub Docs](https://docs.github.com/)
- [GitHub Skills](https://skills.github.com/)

---

## Closing

GitHub is not just a "code storage".
It's **a log of developers' thoughts and growth**.

Didn't you feel a little happy when your first `git push` went through?

That feeling is enough.
Next up: branches and merging.
Git transforms from "just a tool" to "a fun instrument".

---

## Contributing

If you have suggestions for improvements or additional content, please submit an Issue or Pull Request!

---

## License

MIT License

---

**Last Updated**: 2025-01-05
**Version**: 3.0.0

**Language**: [Japanese](./README.md) | [English](./README_EN.md)
