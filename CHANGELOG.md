# Changelog

All notable changes to the Esper Skills repository will be documented in this file.

## [2.0.0] - 2026-07-11

### Added
- **`esp-report`**: New skill to enforce taxonomy and standardize reporting schemas across agents.
- **`esp-safety-gate`**: New skill acting as a validation checkpoint, mandating explicit user approval before execution of irreversible changes or broad code scaffolding.

### Changed
- **XML Porting**: Converted the Markdown bodies of all 19 skills into the canonical `<esper_module type="skill">` XML schema to ensure flawless LLM parser interpretation.
- **Modular Workflow Delegation**: Refactored monolithic skills (`esp-audit`, `esp-hunt`, `esp-scaffold`) to actively invoke the new `esp-report`, `esp-safety-gate`, and `esp-orch` skills rather than duplicating logic.
- **YAML Synchronization**: Fixed YAML metadata names across 5 core skills to perfectly match their parent directories.

### Removed
- **Core Absorption**: Deleted `esp-safety-gate`, `esp-report`, and `esp-clarify` from the skills repository. These fundamental behaviors have been absorbed directly into Esper Core as Always-On Rules in `.agents/rules/`.
- **Boilerplate Cleanup**: Purged three incomplete placeholder skills (`esp-fetch-docs`, `esp-lint`, `esp-tracker`) to maintain workspace hygiene.

## [1.2.0] - 2026-07-10

### Changed
- **Standard Compliance & Agent-Driven Invocation**: Refactored the repository structure to comply strictly with the standard Antigravity skills placement convention (`~/.gemini/config/skills/`). Furthermore, explicitly redefined Esper skills as **agent-driven modules** (loaded via standard prompts and `view_file` calls) rather than UI-driven slash-command skills (`/`). This allows the repository to be cloned safely into a subfolder (`esper-skills/`), keeping the root skills directory clean and avoiding Git conflicts.
- **Update Scripts**: Added `update.ps1` and `update.sh` to allow users to fetch the latest skills via `git pull` easily.

## [1.1.0] - 2026-07-10

### Added
- **`esp-cpt`**: Added new skill to generate discrete checkpoint snapshots to save intent and current project state. Includes a prompt asking the user for a short slug and a Git tag to link the checkpoint to Git history.
- **`esp-note`**: Added new skill to create pull-based, persistent sticky notes without bloating the context window.
- **`esp-meta-context`**: Added a strict rule requiring the agent to ALWAYS prompt the user for explicit permission before executing AST mapping or RAG indexing.

## [1.0.0] - 2026-07-09

### Added
- Initial repository structure and core Esper skills.
