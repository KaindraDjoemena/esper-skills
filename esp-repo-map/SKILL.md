---
name: esp-repo-map
description: Extracts lightweight AST mappings of repositories directly into shared_context/.
---

# `esp-repo-map` Skill

## Workflow

1. **Locate Target Context**:
   - Check the project root for `<project-root>/.esper/shared_context/`.
   - If the folder does not exist, gracefully create it. **CRITICAL:** Whenever you create this folder, explicitly notify the user and strongly suggest they add `.esper/` to their `.gitignore`.
2. **Execution**:
   - Parse the repository to extract an Abstract Syntax Tree (classes, method signatures, exports).
- Save the lightweight AST map to `<project-root>/.esper/shared_context/repo-map.md`. **CRITICAL:** The file MUST include a YAML frontmatter (e.g., `type: repo-map`, `date: ...`) to enable structured querying.
