---
name: esp-orch
description: A skill to orchestrate multiple subagents for a large task using Esper's orchestration capabilities.
---
<esper_module type="skill">
  <name>esp-orch Skill</name>
  <purpose>Delegate complex tasks across multiple parallel or hierarchical subagents while minimizing context bottlenecking and token bloat.</purpose>
  <instructions>
<execution_steps>
<step>Analyze Task: Determine if the task can be parallelized (Flat delegation) or requires sequential dependencies (Hierarchical delegation). Delegate only when a task requires specialized skills, has independent components, or is highly complex.</step>
    <step>Context Sharing &amp; Handoffs: Stateful Handoffs: Pass compressed summaries or specific output artifacts between agents instead of raw conversation histories. Shared Workspace: Utilize a centralized blackboard (e.g. templates/shared-scratchpad.md) for agents to read/write persistent findings.</step>
    <step>Execution: Invoke subagents with strict, scoped prompts. Wait for completion and synthesize the findings.</step>
</execution_steps>
</instructions>
</esper_module>
