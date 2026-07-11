---
name: esp-repo-map
description: Extracts lightweight AST mappings of repositories directly into shared_context/.
---
<esper_module type="skill">
  <name>esp-repo-map Skill</name>
  <instructions>
<execution_steps>
<step>Locate Target Context: Check the project root for &lt;project-root&gt;/.esper/shared_context/. If the folder does not exist, gracefully create it. CRITICAL: Whenever you create this folder, explicitly notify the user and strongly suggest they add .esper/ to their .gitignore.</step>
    <step>Execution: Parse the repository to extract an Abstract Syntax Tree (classes, method signatures, exports). Save the lightweight AST map to &lt;project-root&gt;/.esper/shared_context/repo-map.md. CRITICAL: The file MUST include a YAML frontmatter (e.g., type: repo-map, date: ...) to enable structured querying.</step>
</execution_steps>
</instructions>
</esper_module>
