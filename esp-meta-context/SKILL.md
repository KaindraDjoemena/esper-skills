---
name: esp-meta-context
description: Orchestrates memory management by coordinating esp-rag and esp-repo-map.
---
<esper_module type="skill">
  <name>esp-meta-context Skill</name>
  <purpose>A meta-skill that manages a project's .esper/shared_context/ by coordinating other memory skills.</purpose>
  <instructions>
<execution_steps>
<step>Initialize/Verify: Check if &lt;project-root&gt;/.esper/shared_context/ exists. If it needs to be created, create it gracefully and immediately prompt the user to add .esper/ to .gitignore.</step>
    <step>Coordinate Updates: CRITICAL: You must ALWAYS prompt the user for explicit permission before executing AST mapping or RAG indexing. Utilize esp-repo-map to refresh the AST map if the codebase has changed significantly. Utilize esp-rag to index any new critical bug fixes, logs, or architectural decisions.</step>
    <step>Synthesis: Maintain a master index or summary file within the context directory so that future agents can quickly retrieve relevant state.</step>
</execution_steps>
</instructions>
</esper_module>
