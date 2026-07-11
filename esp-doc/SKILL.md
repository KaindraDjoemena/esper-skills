---
name: esp-doc
description: Generates high-quality, structured documentation while enforcing progressive disclosure and context tiering.
---
<esper_module type="skill">
  <name>esp-doc Skill</name>
  <purpose>Produce rigorous, beautifully formatted, and deeply useful documentation without overwhelming the context window.</purpose>
  <instructions>
<execution_steps>
<step>Mandatory Confirmation Phase: Before writing any documentation, you MUST explicitly ask the user how the documentation should be structured and scoped. Ask them to choose: Scope: Per feature, per file, or entire project? Structure: One monolithic file, or separated folders with an index?</step>
    <step>Apply Formatting Best Practices: Layered Context: Structure the document in three tiers: Discovery (metadata/names), Activation (core instructions), and Execution (deep details/examples). TOC/Index Pattern: If dealing with large systems, avoid encyclopedic files. Create lightweight index files that link directly to specialized sub-files. Progressive Disclosure: Keep references shallow. Link directly from the index rather than deeply nested structures. Grounding: Base instructions on real-world constraints from the codebase rather than vague platitudes.</step>
    <step>Execution: Execute the documentation strategy based on the user's approved structure.</step>
</execution_steps>
</instructions>
</esper_module>
