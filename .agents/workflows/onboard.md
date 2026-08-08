---
description: Onboarding guide for developers working on the zerogravity plugin.
---

# Developer Onboarding Guide

## 1. Setup Environment
1. Install Antigravity CLI (agy).
2. Install `zero` globally on your machine: `npm install -g @gitlawb/zero` (or equivalent).
3. Symlink this project to `~/.gemini/config/plugins/zerogravity`.

## 2. Structure Overview
- Write skills in `skills/` with the filename `SKILL.md`.
- Register slash commands in `commands/` as `.toml` files.
