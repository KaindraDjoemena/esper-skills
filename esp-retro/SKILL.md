---
name: retrospective
description: A skill to perform system retrospectives to evaluate work completed and learn from mistakes.
---

# Retrospective Skill

## Purpose
Trigger a systemic self-evaluation of the agent's recent performance to improve future operations.

## Instructions
1. **Review Transcripts:** Review recent transcripts or scratchpads for the completed work.
2. **Identify Issues:** Identify consistent failure modes, logic gaps, or hallucinations.
3. **Incorporate Reflection:**
   - When a hallucination or failure is detected, identify the systemic cause (e.g. missing context, faulty assumption) rather than just a surface-level error.
   - Record the failure in a persistent memory structure for future tasks.
   - Prioritize permanent adjustments to checklists over temporary fixes in scratchpads.
4. **Apply Reporting Taxonomy:** Generate a report detailing the root causes. Use the standardized Esper taxonomy for any identified flaws in the system:
   - **Severity:** Critical (immediate action), High (serious issues), Medium (maintainability/abstraction), Low (minor), Nit (cosmetic).
   - **Confidence:** Confirmed (direct evidence), Likely (strong evidence but some assumptions), Speculative (limited evidence).
5. **Recommend Updates:** Recommend structural updates to Esper's principles or checklists.

## Esper Dependencies
- workflows/agent-communication.md
- workflows/revision.md
- checklists/self-review.md
- templates/research-report.md
- principles/reflection.md
- principles/reporting/taxonomy.md
