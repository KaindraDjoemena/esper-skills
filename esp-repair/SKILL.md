---
name: esp-repair
description: Debugs and repairs broken code by safely running tests in an isolated environment.
---

# esp-repair

## Purpose
This skill repairs broken code, syntax errors, and test failures in an automated manner.

## Instructions
1. Analyze the failing test output or error logs to understand the issue.
2. Formulate a hypothesis for the root cause and a plan to fix it.
3. Implement the proposed fix.
4. **CRITICAL INSTRUCTION**: You must enforce running test loops in an isolated sandboxed environment. Do not execute arbitrary, unverified test code directly on the host machine. Ensure the sandbox resets properly between iterations.
5. Iterate until the tests pass within the sandbox.
6. Summarize the root cause and the fix that was applied.
