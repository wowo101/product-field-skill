---
name: pf:check
description: Validate consistency and core/context fit using the relational grammar
argument-hint: "<product-name>"
---

<context>
Product name: $ARGUMENTS (required)

@reference/relations.md
</context>

<objective>
Test whether the product's description is consistent and whether the innovation itself is coherent. This is the analytical step — rigorous but not academic.

**Steps:**

1. **Read the canvas.** Load `products/<product-name>/canvas.md`. Pull out the primary facts for each aspect.

2. **Construct the four validation sentences.** Fill in each template with actual canvas content:

   - **Desirability:** "[product] solves [problem] which impedes [motivations] that move [users]"
   - **Viability:** "[goals] lead [drivers] to shape [uniqueness] that differentiates [product]"
   - **Feasibility:** "[enablers] empower [production] to build [solution] realized in [product]"
   - **Marketability:** "[distribution] reaches [customers] who replace [alternatives] with [product]"

   Use the primary facts. If an aspect is empty, note the gap — the sentence can't be completed.

3. **Evaluate each sentence.** For each:
   - Does it make sense when read as a whole? Does it flow?
   - Does each link in the chain hold? (Use the "when it breaks" guidance from relations.md)
   - Is there evidence supporting the claim, or is it wishful thinking?
   - Rate: holds / partially holds / breaks

4. **Test the context chain.** Walk through the circular chain (GOALS→DRIVERS→ENABLERS→PRODUCTION→DISTRIBUTION→CUSTOMERS→USERS→MOTIVATIONS→GOALS). For each link, does the relationship hold with actual canvas content?

5. **Surface tensions.** Look for aspects pulling in different directions. These are insights, not errors:
   - GOALS want rapid growth but ENABLERS are limited
   - USERS want simplicity but the solution is complex
   - CUSTOMERS want low price but PRODUCTION is expensive
   Present tensions clearly. Don't try to resolve them — they reveal strategic choices.

6. **Check for product convolution.** If validation sentences produce unrelated statements that don't connect to each other, the canvas may be describing two products merged into one. Flag this possibility.

7. **Write check.md.** Create `products/<product-name>/check.md` from the template. Fill in all findings.

8. **Report and recommend.** Summarize:
   - Overall core/context fit: strong / partial / weak
   - Which sentences hold, which break
   - Key tensions identified
   - Specific aspects to revisit (go back to Map) with the exact broken links as guidance
   - Whether it's worth proceeding to Find, or whether gaps should be filled first

**Tone:** Direct and honest. If the feasibility sentence breaks, say so clearly. But frame it constructively — "This breaks here, which means..." not "This is wrong."

**Writes:** `products/<name>/check.md`
</objective>
