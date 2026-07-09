---
name: esp-note
description: Create pull-based, persistent sticky notes and handovers without bloating the context window.
---

# `esp-note` Skill

## Purpose
A lightweight skill for dropping targeted, pull-based markdown files into `.esper/shared_context/notes/` for future reference. It operates entirely independently to prevent dependency hell.

## Workflow

1. **Locate Target Context**:
   - Determine if the note belongs globally (`~/.gemini/esper/shared_context/notes/`) or locally (`<project-root>/.esper/shared_context/notes/`).
   - If the folder does not exist, create it gracefully. Remind the user to update `.gitignore` if creating a local folder.
2. **Draft the Note**:
   - Ensure the note is concise.
   - Format it as markdown.
   - **CRITICAL:** You must include YAML frontmatter with `type: note`, the current `date`, and relevant `tags` (e.g., `tags: [auth, architecture]`).
3. **Save and Index**:
   - Save the file with a descriptive, lowercase slug filename (e.g., `2026-07-09-auth-decision.md`).
   - Open `.esper/shared_context/notes-manifest.md` and append the note's date, title, and tags.
   
## Context Bloat Rule
- **Never auto-load the `notes/` directory.** If you need historical context, read `notes-manifest.md` first and only use tool calls to retrieve notes that match your target tags.
