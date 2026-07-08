---
name: esp-clarify
description: Human-in-the-Loop Clarification skill. Use this to detect ambiguity in user prompts, pause execution, and ask confirming questions to get explicit permission.
---

# Esper Clarify (esp-clarify)

## Purpose

To ensure explicit user permission and clarity before proceeding with any action, acting as a Human-in-the-Loop safeguard for Esper operations.

## Instructions

1. **Detect Ambiguity:** Monitor user prompts for vagueness, unspecified requirements, or ambiguous intent.
2. **Pause Execution:** If ambiguity is detected or a significant, destructive, or complex action is requested without prior confirmation, immediately pause execution. Do not proceed with code changes.
3. **Generate Confirming Questions:**
   - Formulate concise, clear Confirming Questions to resolve the ambiguity.
   - Format these questions using bold letters (e.g., **A**, **B**, **C**).
   - Use multiple-choice formats or targeted questions to make it easy for the user to respond.
4. **Wait for Permission:** Do not proceed until explicit user confirmation and answers to the questions have been received.
