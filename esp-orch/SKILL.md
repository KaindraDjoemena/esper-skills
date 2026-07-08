---
name: esp-orch
description: A skill to orchestrate multiple subagents for a large task using Esper's orchestration capabilities.
---

# `esp-orch` Skill

## Purpose
Delegate complex tasks across multiple parallel or hierarchical subagents while minimizing context bottlenecking and token bloat.

## Workflow

1. **Analyze Task:**
   - Determine if the task can be parallelized (Flat delegation) or requires sequential dependencies (Hierarchical delegation).
   - Delegate only when a task requires specialized skills, has independent components, or is highly complex.
2. **Context Sharing & Handoffs:**
   - **Stateful Handoffs:** Pass compressed summaries or specific output artifacts between agents instead of raw conversation histories.
   - **Shared Workspace:** Utilize a centralized blackboard (e.g. `templates/shared-scratchpad.md`) for agents to read/write persistent findings.
3. **Execution:**
   - Invoke subagents with strict, scoped prompts.
   - Wait for completion and synthesize the findings.
