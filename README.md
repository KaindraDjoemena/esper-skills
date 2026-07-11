# Esper Skills

This repository contains modular skills designed to extend the capabilities of the Esper OS. Rather than bundling these natively, they are maintained separately to prevent bloat and dependency hell.

> [!WARNING]
> These skills are highly autonomous. Always rely on Esper's inherent Human-in-the-Loop confirmations (`esp-clarify`) before allowing agents to execute irreversible tasks.

## Available Skills

- **`esp-ask`**: Copilot-style read-only assistant for answering questions directly without agentic execution.
- **`esp-audit`**: Comprehensive audit of project architecture, security, and scope.
- **`esp-cpt`**: Generates discrete checkpoint snapshots to save intent, todos, and project state.
- **`esp-doc`**: Generates high-quality, structured documentation using progressive disclosure.
- **`esp-edit`**: Applies precise line-range diffs and regex for safe, surgical code modification.
- **`esp-hunt`**: Analyzes code to find edge cases, boundary conditions, and missing tests.
- **`esp-meta-context`**: Orchestrates project memory management by coordinating `esp-rag` and `esp-repo-map`.
- **`esp-note`**: Creates pull-based, persistent sticky notes without bloating the context window.
- **`esp-orch`**: Orchestrates multiple subagents for complex tasks using safe delegation.
- **`esp-plan`**: Formulates detailed implementation plans before writing code.
- **`esp-rag`**: Retrieves from and writes to the `shared_context/` memory bank for persistent state.
- **`esp-repair`**: Iterative test-driven repair looping executed in an isolated sandbox.
- **`esp-repo-map`**: Extracts lightweight AST mappings of repositories directly into `shared_context/`.
- **`esp-retro`**: Performs system retrospectives to evaluate work completed.
- **`esp-scaffold`**: Scaffolds new features based on strict architectural alignment.
- **`esp-update-changelog`**: Automatically updates `CHANGELOG.md` based on project history and diffs.

## Installation

To install these skills globally, simply clone this repository directly into your global skills directory under a dedicated `esper-skills` folder:

```bash
git clone https://github.com/KaindraDjoemena/esper-skills.git ~/.gemini/config/skills/esper-skills
```

Because these skills are designed to be dynamically loaded by the Esper AI agent (rather than invoked as manual UI slash commands), nesting them inside an `esper-skills` subfolder keeps your root directory perfectly clean and prevents Git conflicts with other third-party UI skills.

## Updating
You can easily pull the latest workflows using the included update scripts:

### Windows (PowerShell)
```powershell
cd ~/.gemini/config/skills/esper-skills
.\update.ps1
```

### macOS / Linux
```bash
cd ~/.gemini/config/skills/esper-skills
./update.sh
```
