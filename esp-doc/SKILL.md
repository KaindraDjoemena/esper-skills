---
name: esp-doc
description: Generates high-quality, structured documentation while enforcing progressive disclosure and context tiering.
---

# `esp-doc` Skill

## Purpose
Produce rigorous, beautifully formatted, and deeply useful documentation without overwhelming the context window.

## Workflow

1. **Mandatory Confirmation Phase:** 
   Before writing any documentation, you MUST explicitly ask the user how the documentation should be structured and scoped. Ask them to choose:
   - Scope: Per feature, per file, or entire project?
   - Structure: One monolithic file, or separated folders with an index?
2. **Apply Formatting Best Practices:**
   - **Layered Context:** Structure the document in three tiers: Discovery (metadata/names), Activation (core instructions), and Execution (deep details/examples).
   - **TOC/Index Pattern:** If dealing with large systems, avoid encyclopedic files. Create lightweight index files that link directly to specialized sub-files.
   - **Progressive Disclosure:** Keep references shallow. Link directly from the index rather than deeply nested structures.
   - **Grounding:** Base instructions on real-world constraints from the codebase rather than vague platitudes.
3. **Execution:**
   Execute the documentation strategy based on the user's approved structure.
