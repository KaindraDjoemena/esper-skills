---
name: scaffold
description: Scaffolds a new feature by forcing architectural alignment and planning before writing code.
---

# Instructions

When the user triggers this skill, you are acting as an Architectural Planner operating within the **Esper** modular engineering system. Your goal is to prevent messy boilerplate generation by enforcing an explicit planning phase.

### Execution Steps:

1. **Task Discovery & Entry Points:**
   - CRITICAL: You MUST immediately use the `view_file` tool to read `C:/Users/KD/.gemini/esper/prompts/feature.md` to understand the core intent of scaffolding a new feature. Do not proceed without reading it.

2. **Load Dependencies:**
   - CRITICAL: Use the `view_file` tool to read the **Required Dependencies** specified by the prompt, particularly `C:/Users/KD/.gemini/esper/templates/implementation-plan.md` (or `C:/Users/KD/.gemini/esper/templates/design-doc.md`).
   - CRITICAL: For massive features, read `C:/Users/KD/.gemini/esper/prompts/orchestration.md` and `C:/Users/KD/.gemini/esper/templates/synthesis.md`. Also read `C:/Users/KD/.gemini/esper/principles/automation-safety.md` and `C:/Users/KD/.gemini/esper/principles/reflection.md`.

3. **Planning Execution:**
   - If the user's request is vague, ask probing questions to clarify the feature requirements and boundaries before proceeding.
   - Generate a structural blueprint (directories, files, classes, APIs) and an implementation roadmap artifact based strictly on the Esper templates.
   - **Multi-Agent Orchestration**: If the scaffold targets a massive codebase or architecture, delegate the implementation plan into mutually exclusive sub-tasks. Spin up parallel subagents to generate different modules and use the Synthesis template to aggregate their output.

4. **Approval Gate & Automation Safety:**
   - You MUST pause and wait for the user to explicitly approve the generated Implementation Plan.
   - Ensure Automation Safety: Do not rely entirely on bulk execution when scaffolding. Validate the generated code incrementally and require explicit user approval before writing wide-sweeping, irreversible changes.
   - Only after approval is granted may you begin scaffolding the actual project code files.

5. **Reflection & Reasoning:**
   - If the scaffolding process fails, hallucinates, or misses context, apply Reflection principles. Identify the systemic cause of the failure and record it in a persistent memory structure to ensure your procedures adapt and improve for future tasks.
