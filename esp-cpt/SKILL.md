---
name: esp-cpt
description: Generate a discrete checkpoint snapshot to save intent and current project state.
---
<esper_module type="skill">
  <name>esp-cpt Skill (Esper Checkpoint)</name>
  <purpose>A structured "save state" tool to capture the mental model, immediate todo lists, and strategic roadmap of a project at a specific moment in time.</purpose>
  <instructions>
<execution_steps>
<step>Ask for Slug &amp; Git Tag: CRITICAL: Pause execution and ask the user for a short, descriptive slug for this checkpoint (e.g., auth-fixed or pre-refactor). Also explicitly ask if the user wants you to run git tag &lt;slug&gt; to formally link this checkpoint to the project's Git history.</step>
    <step>Create Checkpoint Directory: Generate a timestamped folder in &lt;project-root&gt;/.esper/shared_context/checkpoints/ formatted as YYYY-MM-DD_HH-MM_&lt;slug&gt;/. If this is the first checkpoint, ensure the directory exists and remind the user to update .gitignore.</step>
    <step>Generate Snapshot Files: Write session-handover.md: Summarize what was just done, what is blocking, and what is next. Write todo-list.md: List the immediate tactical tasks. Write roadmap.md: List the long-term strategic goals.</step>
    <step>Update the Index: Append a 1-sentence summary of this checkpoint to &lt;project-root&gt;/.esper/shared_context/checkpoints/index.md.</step>
</execution_steps>
</instructions>
  <context_bloat_rule>Future agents should read index.md to track momentum, and only load the specific timestamp directory if they need to resume work from that exact moment.</context_bloat_rule>
</esper_module>
