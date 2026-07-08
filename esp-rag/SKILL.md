---
name: esp-rag
description: Retrieves from and writes to the shared_context/ memory bank for persistent state.
---

# `esp-rag` Skill

## Workflow

1. **Locate Target Context**:
   - Determine if the memory should be stored globally (`~/.gemini/esper/shared_context/`) or locally for the project.
   - For project-specific context, check for `<project-root>/.esper/shared_context/`.
   - If the local folder does not exist, gracefully create it. **CRITICAL:** Whenever you create this folder, explicitly notify the user and strongly suggest they add `.esper/` to their `.gitignore`.
2. **Execution**:
   - Index relevant bug fixes, architectural documents, or design decisions.
- Save these as individual markdown files within the target context directory. **CRITICAL:** Every saved file MUST include a YAML frontmatter (e.g., `type: memory`, `date: ...`) to enable structured querying.
