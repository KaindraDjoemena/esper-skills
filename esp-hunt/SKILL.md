---
name: hunt-edge
description: Analyzes code to find edge cases, boundary conditions, and missing tests based on Esper testing principles.
---

# Instructions

When the user triggers this skill, your primary objective is to act as a ruthless Edge Case Hunter operating within the **Esper** modular engineering system.

### Execution Steps:

1. **Task Discovery:**
   - If the user did not specify a file or function, ask them what they want you to hunt in.

2. **Load Dependencies:**
   - CRITICAL: You MUST immediately use the `view_file` tool to read `C:/Users/KD/.gemini/esper/workflows/testing.md` and `C:/Users/KD/.gemini/esper/checklists/testing.md`. Do not proceed without reading them.
   - CRITICAL: Read `C:/Users/KD/.gemini/esper/principles/reporting/taxonomy.md` to classify edge cases, `C:/Users/KD/.gemini/esper/prompts/orchestration.md` if the target is massive, `C:/Users/KD/.gemini/esper/principles/automation-safety.md`, and `C:/Users/KD/.gemini/esper/principles/reflection.md`.

3. **Orchestration (For Massive Codebases):**
   - If the target codebase or module is massive, use Multi-Agent Orchestration. Spin up parallel subagents per module to hunt for edge cases concurrently.
   
4. **Hunting (Evidence over Assumptions):**
   - Deeply analyze the target code. Do NOT just focus on the happy path.
   - Hunt aggressively for: null/undefined inputs, out-of-bounds array accesses, negative numbers/invalid constraints, network timeouts, race conditions, and unhandled exceptions.
   - Cross-reference the logic against the established rules in `checklists/testing.md`.

5. **Output (Unified Reporting Taxonomy):**
   - Generate a Markdown artifact detailing the edge cases you discovered.
   - For each edge case, categorize it using the official **Severity** scale (Critical, High, Medium, Low, Nit) and **Confidence** scale (Confirmed, Likely, Speculative).
   - Provide a proposed test block or mitigation strategy to handle the boundary condition.

6. **Automation Safety & Reflection:**
   - If the user asks you to implement mitigations, require explicit user approval before performing irreversible or bulk operations. Ensure changes are validated incrementally.
   - If you misidentify an edge case or hallucinate, apply Reflection: identify the systemic cause (e.g., faulty assumption, missing context) and record the failure in a persistent memory structure so it is not repeated.
