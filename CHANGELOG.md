# Changelog

All notable changes to the Esper Skills repository will be documented in this file.

## [1.1.0] - 2026-07-10

### Added
- **`esp-cpt`**: Added new skill to generate discrete checkpoint snapshots to save intent and current project state. Includes a prompt asking the user for a short slug and a Git tag to link the checkpoint to Git history.
- **`esp-note`**: Added new skill to create pull-based, persistent sticky notes without bloating the context window.
- **`esp-meta-context`**: Added a strict rule requiring the agent to ALWAYS prompt the user for explicit permission before executing AST mapping or RAG indexing.

## [1.0.0] - 2026-07-09

### Added
- Initial repository structure and core Esper skills.
