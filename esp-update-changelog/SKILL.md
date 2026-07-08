---
name: esp-update-changelog
description: Automatically reads project history and updates the CHANGELOG.md file.
---

# `esp-update-changelog` Skill

## Purpose
Automate the process of updating project changelogs by analyzing recent commits, file modifications, and contextual changes to accurately document project evolution.

## Workflow

1. **Context Gathering:**
   - Use `git status` and `git diff` (if applicable) or read the commit history to identify what has changed since the last release or update.
   - Read the existing `CHANGELOG.md` to understand the current versioning and formatting schema.
2. **Synthesis:**
   - Group changes logically (e.g., Added, Changed, Removed, Fixed).
   - Summarize the changes clearly and concisely.
3. **Execution:**
   - Use file modification tools to update `CHANGELOG.md`.
   - Optionally present the updated changelog to the user for final approval before committing.
