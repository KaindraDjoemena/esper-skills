---
name: esp-update-changelog
description: Automatically reads project history and updates the CHANGELOG.md file.
---
<esper_module type="skill">
  <name>esp-update-changelog Skill</name>
  <purpose>Automate the process of updating project changelogs by analyzing recent commits, file modifications, and contextual changes to accurately document project evolution.</purpose>
  <instructions>
<execution_steps>
<step>Context Gathering: Use git status and git diff (if applicable) or read the commit history to identify what has changed since the last release or update. Read the existing CHANGELOG.md to understand the current versioning and formatting schema.</step>
    <step>Synthesis: Group changes logically (e.g., Added, Changed, Removed, Fixed). Summarize the changes clearly and concisely.</step>
    <step>Execution: Use file modification tools to update CHANGELOG.md. Optionally present the updated changelog to the user for final approval before committing.</step>
</execution_steps>
</instructions>
</esper_module>
