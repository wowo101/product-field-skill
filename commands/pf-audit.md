---
name: pf:audit
description: Check aspect placement — catch facts in the wrong area
argument-hint: "<product-name>"
allowed-tools:
  - Read
  - Write
---

<context>
Product name: $ARGUMENTS (required)

@reference/aspects.md
</context>

<objective>
Review the canvas for misplaced facts. This is a teaching tool for PF literacy — it helps users build intuition for which facts belong where.

**Steps:**

1. **Read the canvas.** Load `products/<product-name>/canvas.md`.

2. **Check each fact against aspect definitions.** For every fact in the canvas, compare it against the aspect definition and the "watch for misplacements" section in aspects.md. Ask:
   - Does this fact describe something that fits this aspect's definition?
   - Is there another aspect where it would be a better fit?

3. **Flag potential misplacements.** For each suspected misplacement:
   - Quote the specific fact
   - Explain which aspect it's currently in
   - Suggest where it might belong and why
   - Example: "You have 'dental trade shows' under PRODUCTION. This sounds like it's about reaching customers, which would make it DISTRIBUTION."

4. **Ask the user to confirm each move.** Don't move anything automatically. The user may have a good reason for the current placement, or the fact might genuinely sit at a boundary between two aspects (which is fine — note it).

5. **Update the canvas** with confirmed moves. Preserve epistemic status tags and primary/supporting ranking when moving facts.

6. **Report.** Summarize what was moved, what was kept in place, and any boundary cases noted. If moves were made, suggest re-running `/pf:check` since changed placements affect validation sentences.

**Judgment calls:**

- Some facts legitimately sit at boundaries (e.g., a partner could be both ENABLERS and DISTRIBUTION). Note these rather than forcing a choice.
- Don't be overly pedantic. If a fact is in a reasonable place, leave it alone. Only flag clear misplacements.
- This is not about being right — it's about helping the user think more precisely about their product.

**Writes:** `products/<name>/canvas.md` (only with user-confirmed changes)
</objective>
