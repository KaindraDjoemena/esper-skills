---
name: esp-meta-context
description: Orchestrates memory management by coordinating esp-rag and esp-repo-map.
---

# `esp-meta-context` Skill

## Purpose
A meta-skill that manages a project's `.esper/shared_context/` by coordinating other memory skills.

## Workflow

1. **Initialize/Verify**:
   - Check if `<project-root>/.esper/shared_context/` exists. If it needs to be created, create it gracefully and immediately prompt the user to add `.esper/` to `.gitignore`.
2. **Coordinate Updates**:
   - Utilize `esp-repo-map` to refresh the AST map if the codebase has changed significantly.
   - Utilize `esp-rag` to index any new critical bug fixes, logs, or architectural decisions.
3. **Synthesis**:
   - Maintain a master index or summary file within the context directory so that future agents can quickly retrieve relevant state.
