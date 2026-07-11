---
name: esp-scaffold
description: Scaffolds a new feature by forcing architectural alignment and planning before writing code.
---
<esper_module type="skill">
  <instructions>
    <role>When the user triggers this skill, you are acting as an Architectural Planner operating within the Esper modular engineering system. Your goal is to prevent messy boilerplate generation by enforcing an explicit planning phase.</role>
    <execution_steps>
      <step>Task Discovery &amp; Entry Points: CRITICAL: You MUST immediately use the view_file tool to read C:/Users/KD/.gemini/esper/prompts/feature.md to understand the core intent of scaffolding a new feature. Do not proceed without reading it.</step>
      <step>Load Dependencies: CRITICAL: Use the view_file tool to read the Required Dependencies specified by the prompt, particularly C:/Users/KD/.gemini/esper/templates/implementation-plan.md (or C:/Users/KD/.gemini/esper/templates/design-doc.md). CRITICAL: For massive features, read C:/Users/KD/.gemini/esper/templates/synthesis.md. Also read C:/Users/KD/.gemini/esper/principles/reflection.md.</step>
      <step>Planning Execution: If the user's request is vague, ask probing questions to clarify the feature requirements and boundaries before proceeding. Generate a structural blueprint (directories, files, classes, APIs) and an implementation roadmap artifact based strictly on the Esper templates. Multi-Agent Orchestration: If the scaffold targets a massive codebase or architecture, invoke the esp-orch skill to delegate the implementation plan into mutually exclusive sub-tasks and use the Synthesis template to aggregate output.</step>
      <step>Approval Gate: Invoke the esp-safety-gate skill to pause and wait for the user to explicitly approve the generated Implementation Plan before scaffolding the actual project code files.</step>
      <step>Reflection &amp; Reasoning: If the scaffolding process fails, hallucinates, or misses context, apply Reflection principles. Identify the systemic cause of the failure and record it in a persistent memory structure to ensure your procedures adapt and improve for future tasks.</step>
    </execution_steps>
  </instructions>
</esper_module>
