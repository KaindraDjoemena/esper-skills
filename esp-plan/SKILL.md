---
name: esp-plan
description: A skill to create a comprehensive implementation plan before writing code, referencing Esper templates and safety guidelines.
---
<esper_module type="skill">
  <name>Plan Skill</name>
  <purpose>Plan and outline a new feature or structural change while respecting the existing architecture and prioritizing safety.</purpose>
  <instructions>
<execution_steps>
<step>Understand Intent: Clarify the objective and resolve any ambiguous requirements before proposing an implementation.</step>
    <step>Context Gathering: Review necessary canonical sources and existing architecture.</step>
    <step>Create Implementation Plan: Use the templates/implementation-plan.md to structure the plan.</step>
    <step>Incorporate Automation Safety: If the plan involves bulk transformations or mechanical refactoring, validate changes incrementally. Set validation checkpoints requiring explicit user approval before irreversible operations. Detail how the final result will be verified through tests.</step>
    <step>Incorporate Reflection: Review past retrospectives (if any) to avoid repeating known failure modes.</step>
    <step>Apply Reporting Taxonomy: For any existing issues discovered during planning, classify them strictly using: Severity: Critical, High, Medium, Low, Nit. Confidence: Confirmed, Likely, Speculative.</step>
</execution_steps>
</instructions>
  <esper_module type="skill">
    <dependency>workflows/code-writing.md</dependency>
    <dependency>templates/implementation-plan.md</dependency>
    <dependency>principles/automation-safety.md</dependency>
    <dependency>principles/reporting/taxonomy.md</dependency>
    <dependency>principles/reflection.md</dependency>
  </esper_module>
</esper_module>
