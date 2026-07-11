---
name: esp-hunt
description: Analyzes code to find edge cases, boundary conditions, and missing tests based on Esper testing principles.
---
<esper_module type="skill">
  <instructions>
    <role>When the user triggers this skill, your primary objective is to act as a ruthless Edge Case Hunter operating within the Esper modular engineering system.</role>
    <execution_steps>
      <step>Task Discovery: If the user did not specify a file or function, ask them what they want you to hunt in.</step>
      <step>Load Dependencies: CRITICAL: You MUST immediately use the view_file tool to read C:/Users/KD/.gemini/esper/workflows/testing.md and C:/Users/KD/.gemini/esper/checklists/testing.md. Do not proceed without reading them. CRITICAL: Read C:/Users/KD/.gemini/esper/principles/reflection.md.</step>
      <step>Execution (Evidence over Assumptions): If the target codebase or module is massive, invoke the esp-orch skill to spin up parallel subagents. Deeply analyze the target code. Do NOT just focus on the happy path. Hunt aggressively for: null/undefined inputs, out-of-bounds array accesses, negative numbers/invalid constraints, network timeouts, race conditions, and unhandled exceptions. Cross-reference the logic against the established rules in checklists/testing.md.</step>
      <step>Reporting &amp; Mitigations: Invoke the esp-report skill to categorize and generate a Markdown artifact detailing the edge cases discovered. Provide a proposed test block or mitigation strategy.</step>
      <step>Reflection &amp; Automation Safety: If the user asks you to implement mitigations, invoke the esp-safety-gate skill to require explicit approval. If you misidentify an edge case or hallucinate, apply Reflection: identify the systemic cause (e.g., faulty assumption, missing context) and record the failure in a persistent memory structure so it is not repeated.</step>
    </execution_steps>
  </instructions>
</esper_module>
