# Esper Skills

This repository contains modular skills designed to extend the capabilities of the Esper OS. Rather than bundling these natively, they are maintained separately to prevent bloat and dependency hell.

> [!WARNING]
> These skills are highly autonomous. Always rely on Esper's inherent Human-in-the-Loop confirmations (`esp-clarify`) before allowing agents to execute irreversible tasks.

## Available Skills

- **`esp-ask`**: Copilot-style read-only assistant for answering questions directly without agentic execution.
- **`esp-audit`**: Comprehensive audit of project architecture, security, and scope.
- **`esp-clarify`**: Human-in-the-Loop Clarification skill to resolve ambiguity safely before execution.
- **`esp-cpt`**: Generates discrete checkpoint snapshots to save intent, todos, and project state.
- **`esp-doc`**: Generates high-quality, structured documentation using progressive disclosure.
- **`esp-edit`**: Applies precise line-range diffs and regex for safe, surgical code modification.
- **`esp-fetch-docs`**: Headless web browsing for fetching external documentation to avoid hallucination.
- **`esp-hunt`**: Analyzes code to find edge cases, boundary conditions, and missing tests.
- **`esp-lint`**: Pre-commit validation and formatting enforcement to match project styling.
- **`esp-meta-context`**: Orchestrates project memory management by coordinating `esp-rag` and `esp-repo-map`.
- **`esp-note`**: Creates pull-based, persistent sticky notes without bloating the context window.
- **`esp-orch`**: Orchestrates multiple subagents for complex tasks using safe delegation.
- **`esp-plan`**: Formulates detailed implementation plans before writing code.
- **`esp-rag`**: Retrieves from and writes to the `shared_context/` memory bank for persistent state.
- **`esp-repair`**: Iterative test-driven repair looping executed in an isolated sandbox.
- **`esp-repo-map`**: Extracts lightweight AST mappings of repositories directly into `shared_context/`.
- **`esp-retro`**: Performs system retrospectives to evaluate work completed.
- **`esp-scaffold`**: Scaffolds new features based on strict architectural alignment.
- **`esp-tracker`**: Hierarchical task tracking and scratchpad management for long-running workflows.
- **`esp-update-changelog`**: Automatically updates `CHANGELOG.md` based on project history and diffs.

## Installation
Clone this repository to your `.gemini/antigravity-cli/skills` (or equivalent) directory so your agent can discover and invoke them on demand.
