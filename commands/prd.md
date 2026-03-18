---
name: pf:prd
description: Derive a Product Requirements Document from a validated canvas
argument-hint: "<product-name>"
allowed-tools:
  - Read
  - Write
---

<context>
Product name: $ARGUMENTS (required)
</context>

<objective>
Generate a PRD from a validated product canvas. The PRD is an engineering handoff document — it translates PF analysis into requirements.

**Prerequisites:** Both check.md and find.md must exist for this product. If either is missing, **refuse** and explain why:
- Without check → requirements would be based on an unvalidated description
- Without find → requirements would lack risk assessment and priority signals

Tell the user to run `/pf:check` and `/pf:find` first.

**Steps:**

1. **Read all product files.** Load:
   - `products/<product-name>/canvas.md`
   - `products/<product-name>/check.md`
   - `products/<product-name>/find.md`
   - `templates/prd.md` for the output structure

2. **Extract problem statement.** From the canvas problem aspect (primary facts). Frame it from the user's perspective — what they face, why it matters, how painful it is. Include evidence from check (does the desirability sentence hold?).

3. **Extract users.** From USERS aspect. Distinguish primary and secondary user segments. Include behavioral context, not just demographics.

4. **Extract solution.** From solution aspect. Describe what the product does, its core mechanism, key components. Derive scope from primary vs. supporting facts — primary facts are v1 scope, supporting facts are future consideration.

5. **Extract uniqueness.** From uniqueness aspect. What differentiates this product from alternatives.

6. **Derive requirements.** Transform canvas facts into requirements:
   - Each primary fact in solution → functional requirement
   - Constraints from ENABLERS and PRODUCTION → non-functional requirements
   - Tag each requirement with source aspect and epistemic confidence
   - Priority based on: primary facts > supporting; verified > assumed

7. **Flag risks.** From find.md:
   - Unresolved weaknesses → risks with severity ratings
   - Load-bearing assumptions → open questions that need answers before or during build
   - Broken validation sentence links → structural risks

8. **Derive success criteria.** From GOALS and MOTIVATIONS:
   - What does success look like for the organization? (from GOALS)
   - What does success look like for users? (from MOTIVATIONS)
   - Turn these into measurable criteria where possible

9. **Note dependencies.** From ENABLERS and PRODUCTION — what needs to be in place before build can start.

10. **Write prd.md.** Create `products/<product-name>/prd.md` from the template.

11. **Report.** Summary of what was generated, key risks flagged, and any open questions that should be resolved before engineering starts.

**Tone:** Precise and engineering-oriented. This document crosses the boundary from product thinking to engineering execution. Be specific about what needs to be built, honest about what's uncertain, and clear about priority.

**Writes:** `products/<name>/prd.md`
</objective>
