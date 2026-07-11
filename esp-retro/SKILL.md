---
name: esp-retro
description: A skill to perform system retrospectives to evaluate work completed and learn from mistakes.
---
<esper_module type="skill">
  <name>Retrospective Skill</name>
  <purpose>Trigger a systemic self-evaluation of the agent's recent performance to improve future operations.</purpose>
  <instructions>
<execution_steps>
<step>Review Transcripts: Review recent transcripts or scratchpads for the completed work.</step>
    <step>Identify Issues: Identify consistent failure modes, logic gaps, or hallucinations.</step>
    <step>Incorporate Reflection: When a hallucination or failure is detected, identify the systemic cause (e.g. missing context, faulty assumption) rather than just a surface-level error. Record the failure in a persistent memory structure for future tasks. Prioritize permanent adjustments to checklists over temporary fixes in scratchpads.</step>
    <step>Apply Reporting Taxonomy: Generate a report detailing the root causes. Use the standardized Esper taxonomy for any identified flaws in the system: Severity: Critical (immediate action), High (serious issues), Medium (maintainability/abstraction), Low (minor), Nit (cosmetic). Confidence: Confirmed (direct evidence), Likely (strong evidence but some assumptions), Speculative (limited evidence).</step>
    <step>Recommend Updates: Recommend structural updates to Esper's principles or checklists.</step>
</execution_steps>
</instructions>
  <esper_module type="skill">
    <dependency>workflows/agent-communication.md</dependency>
    <dependency>workflows/revision.md</dependency>
    <dependency>checklists/self-review.md</dependency>
    <dependency>templates/research-report.md</dependency>
    <dependency>principles/reflection.md</dependency>
    <dependency>principles/reporting/taxonomy.md</dependency>
  </esper_module>
</esper_module>
