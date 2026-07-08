---
name: plan
description: A skill to create a comprehensive implementation plan before writing code, referencing Esper templates and safety guidelines.
---

# Plan Skill

## Purpose
Plan and outline a new feature or structural change while respecting the existing architecture and prioritizing safety.

## Instructions
1. **Understand Intent:** Clarify the objective and resolve any ambiguous requirements before proposing an implementation.
2. **Context Gathering:** Review necessary canonical sources and existing architecture.
3. **Create Implementation Plan:** Use the `templates/implementation-plan.md` to structure the plan.
4. **Incorporate Automation Safety:**
   - If the plan involves bulk transformations or mechanical refactoring, validate changes incrementally.
   - Set validation checkpoints requiring explicit user approval before irreversible operations.
   - Detail how the final result will be verified through tests.
5. **Incorporate Reflection:**
   - Review past retrospectives (if any) to avoid repeating known failure modes.
6. **Apply Reporting Taxonomy:** For any existing issues discovered during planning, classify them strictly using:
   - **Severity:** Critical, High, Medium, Low, Nit.
   - **Confidence:** Confirmed, Likely, Speculative.

## Esper Dependencies
- workflows/code-writing.md
- templates/implementation-plan.md
- principles/automation-safety.md
- principles/reporting/taxonomy.md
- principles/reflection.md
