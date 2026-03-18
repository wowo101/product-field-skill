---
name: pf:consolidate
description: Capture insights from conversation into the canvas
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
Extract PF-relevant insights from the current conversation and consolidate them into the canvas. Use this after a free-flowing discussion that touched on product topics without formally mapping them.

**Steps:**

1. **Review the conversation.** Scan the conversation history for facts, decisions, and insights that are relevant to the product. Look for:
   - Statements about users, their problems, or motivations
   - Decisions about what to build or how
   - Mentions of competitors, market conditions, or distribution
   - Strategic direction, goals, or organizational context
   - Technical capabilities, constraints, or production details

2. **Read the current canvas.** Load `products/<product-name>/canvas.md`.

3. **Extract and classify.** For each relevant insight:
   - Map it to the right aspect using definitions from aspects.md
   - Tag with epistemic status based on how it came up in conversation
   - Classify as Primary or Supporting

4. **Show the diff.** Present what would change:
   - **New facts** — things not currently in the canvas
   - **Reinforced facts** — things already in the canvas that the conversation strengthened (consider upgrading epistemic status)
   - **Contradictions** — things that conflict with what's in the canvas
   - **Upgrades** — facts whose epistemic status should change (e.g., `[assumed]` → `[believed]` because the user confirmed it)

5. **Get confirmation.** Show the proposed changes and ask the user to confirm before writing. They may want to adjust wording, skip some items, or change rankings.

6. **Update the canvas** with confirmed changes.

7. **Optionally update the backlog.** If the conversation revealed new work items (gaps to fill, assumptions to test, things to research), offer to add them to `backlog.md`.

**Tone:** Helpful and organized. You're acting as a note-taker who also understands the PF structure — catching things the user said in passing and putting them in the right place.

**Writes:** `products/<name>/canvas.md`, optionally `backlog.md`
</objective>
