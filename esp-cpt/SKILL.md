---
name: esp-cpt
description: Generate a discrete checkpoint snapshot to save intent and current project state.
---

# `esp-cpt` Skill (Esper Checkpoint)

## Purpose
A structured "save state" tool to capture the mental model, immediate todo lists, and strategic roadmap of a project at a specific moment in time.

## Workflow

1. **Ask for Slug & Git Tag**:
   - **CRITICAL**: Pause execution and ask the user for a short, descriptive slug for this checkpoint (e.g., `auth-fixed` or `pre-refactor`).
   - Also explicitly ask if the user wants you to run `git tag <slug>` to formally link this checkpoint to the project's Git history.
2. **Create Checkpoint Directory**:
   - Generate a timestamped folder in `<project-root>/.esper/shared_context/checkpoints/` formatted as `YYYY-MM-DD_HH-MM_<slug>/`.
   - If this is the first checkpoint, ensure the directory exists and remind the user to update `.gitignore`.
3. **Generate Snapshot Files**:
   - Write `session-handover.md`: Summarize what was just done, what is blocking, and what is next.
   - Write `todo-list.md`: List the immediate tactical tasks.
   - Write `roadmap.md`: List the long-term strategic goals.
4. **Update the Index**:
   - Append a 1-sentence summary of this checkpoint to `<project-root>/.esper/shared_context/checkpoints/index.md`.
   
## Context Bloat Rule
- Future agents should read `index.md` to track momentum, and only load the specific timestamp directory if they need to resume work from that exact moment.
