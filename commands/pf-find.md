---
name: pf:find
description: Evaluate strengths and weaknesses, generate force field, determine character
argument-hint: "<product-name>"
---

<context>
Product name: $ARGUMENTS (required)

@reference/model.md
@reference/aspects.md
@reference/methods.md
</context>

<objective>
Evaluate the product's strengths and weaknesses, generate the force field, determine character, and identify what to do next. This is where the canvas becomes actionable.

**Prerequisites:** The canvas should have reasonable coverage and ideally a check has been run. If `products/<product-name>/check.md` doesn't exist, warn the user and suggest running `/pf:check` first. Proceed if they want to, but note that findings will be less grounded.

**Steps:**

1. **Read canvas and check.** Load `products/<product-name>/canvas.md` and `products/<product-name>/check.md` if it exists.

2. **Evaluate each fact.** For every mapped fact in the canvas context:
   - Judge its contribution to stakeholder impact: positive (+) or negative (−)
   - Weight by epistemic confidence: a `[verified]` strength is more reliable than an `[assumed]` one. A primary `[assumed]` positive is actually a risk — it's load-bearing but unproven
   - Note the reasoning briefly

3. **Aggregate by corner.** Sum up the picture for each corner:
   - **IDEA:** What's the state of goals, drivers, and uniqueness?
   - **VALUE:** How well understood are users, motivations, and the problem?
   - **RESOURCES:** Are enablers, production, and solution in good shape?
   - **MARKET:** How strong are distribution, customers, and alternatives awareness?
   Rate each corner: strong / moderate / weak

4. **Generate the force field.** Along the inside→outside axis:
   - What's **pushing** the product forward from inside? (Strong drivers, clear goals, solid production, good solution)
   - What's **pulling** from outside? (Clear user demand, accessible customers, weak alternatives)
   - What's **dragging** it back? (Missing enablers, weak distribution, unclear problem, assumed facts in critical positions)

5. **Determine character type.** Based on which corner is strongest:
   - Idea Push / Value Pull / Resources Push / Market Pull / Blend
   - Explain what this means for this specific product — not just the generic description, but what it implies about where energy and attention should go

6. **Identify discovery priorities.** Find primary facts tagged `[assumed]` or `[believed]` that are load-bearing — they participate in validation sentences or sit in the strongest/weakest corners. These are the assumptions most worth testing.

7. **Recommend methods.** Based on the weakest corners and biggest gaps, suggest specific methods from methods.md. Connect the recommendation to the gap: "Your VALUE corner is weak — JTBD or Customer Interviews would help you understand whether the problem is real and painful enough."

8. **Identify highest-risk points.** Where on the IDEA→MARKET diagonal are the biggest obstacles? What could derail this product?

9. **Write find.md.** Create `products/<product-name>/find.md` from the template. Fill in all findings.

10. **Report.** Summarize the top findings:
    - Strongest and weakest corners
    - Character type and what it implies
    - Top 3 risks
    - Top 3 next actions
    - Whether the product is ready for PRD generation or needs more work

**Tone:** Strategic and frank. This is where you say "your biggest risk is that your entire VALUE corner is built on assumptions" or "you have strong resources but no evidence anyone wants this." Be constructive but don't sugarcoat.

**Writes:** `products/<name>/find.md`
</objective>
