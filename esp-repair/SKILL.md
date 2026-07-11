---
name: esp-repair
description: Debugs and repairs broken code by safely running tests in an isolated environment.
---
<esper_module type="skill">
  <name>esp-repair</name>
  <purpose>This skill repairs broken code, syntax errors, and test failures in an automated manner.</purpose>
  <instructions>
<execution_steps>
<step>Analyze the failing test output or error logs to understand the issue.</step>
    <step>Formulate a hypothesis for the root cause and a plan to fix it.</step>
    <step>Implement the proposed fix.</step>
    <step>CRITICAL INSTRUCTION: You must enforce running test loops in an isolated sandboxed environment. Do not execute arbitrary, unverified test code directly on the host machine. Ensure the sandbox resets properly between iterations.</step>
    <step>Iterate until the tests pass within the sandbox.</step>
    <step>Summarize the root cause and the fix that was applied.</step>
</execution_steps>
</instructions>
</esper_module>
