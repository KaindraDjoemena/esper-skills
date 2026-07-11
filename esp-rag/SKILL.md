---
name: esp-rag
description: Retrieves from and writes to the shared_context/ memory bank for persistent state.
---
<esper_module type="skill">
  <name>esp-rag Skill</name>
  <instructions>
<execution_steps>
    <step>Native Retrieval (Read Path): Before acting, aggressively use your native semantic search or grep_search tools to query the shared_context/ directories. Search for YAML frontmatter tags or keywords relevant to your current objective to fetch isolated context.</step>
    <step>Locate Target Context: Determine if the memory should be stored globally (~/.gemini/esper/shared_context/) or locally for the project. For project-specific context, check for &lt;project-root&gt;/.esper/shared_context/. If the local folder does not exist, gracefully create it. CRITICAL: Whenever you create this folder, explicitly notify the user and strongly suggest they add .esper/ to their .gitignore.</step>
    <step>Execution (Write Path): Index relevant bug fixes, architectural documents, or design decisions. CRITICAL: Do NOT save to a generic notes.md file. You MUST use a Hierarchical Context structure by saving individual, domain-specific markdown files (e.g., auth-state.md, ui-state.md) within the target context directory.</step>
    <step>Structured Metadata: CRITICAL: Every saved memory file MUST include a strict YAML frontmatter (e.g., type: memory, domain: [specific-domain], date: [YYYY-MM-DD]) to enable future structured querying via native search tools.</step>
</execution_steps>
</instructions>
</esper_module>
