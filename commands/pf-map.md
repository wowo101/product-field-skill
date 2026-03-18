---
name: pf:map
description: Guided adaptive questioning to fill in a product canvas
argument-hint: "<product-name> [aspect]"
---

<context>
Product name: first argument (required)
Aspect: second argument (optional — deep-dive a single aspect)

@reference/model.md
@reference/aspects.md
</context>

<objective>
Help the user fill in their product canvas through adaptive conversation. This is the core exploration command.

**Without an aspect argument — full session:**

1. **Read the canvas.** Load `products/<product-name>/canvas.md`. Show the current state:
   - Which aspects have primary facts
   - Which are thin (only supporting, or only one fact)
   - Which are empty
   Group by corner so the user sees the shape.

2. **Let the user choose.** Don't force a sequence. Ask: "Where would you like to start?" or suggest based on what's empty. If the user doesn't have a preference, suggest starting with whichever corner has the most energy — often VALUE (users and their problems) or IDEA (goals and vision).

3. **Explore each aspect adaptively.** Use the guiding questions from aspects.md as starting points, but:
   - Follow the thread based on what the user reveals
   - Ask follow-up questions inspired by their answers, not just the next question on the list
   - Go where the interesting stuff is
   - 3-4 questions deep on a topic, then check: "Want to go deeper here, or move to another aspect?"
   - The user decides depth. "This is enough" is always valid.

4. **Tag and rank as you go.** For each new fact:
   - Tag with epistemic status based on how the user describes it:
     - Stated with evidence → `[verified]` or `[observed]`
     - Stated with confidence but no evidence → `[believed]`
     - Mentioned tentatively or as a guess → `[assumed]`
     - Described as a goal → `[aspirational]` or `[visionary]`
   - Ask about ranking when multiple facts accumulate: "Which of these are the primary ones — the facts that matter most to this product's success?"

5. **Save periodically.** Update the canvas file after each aspect or natural pause. Don't wait until the end — save progress as you go.

6. **Report at the end.** Show updated state: what's filled, what's still thin, what's empty. Suggest next steps — more mapping, or `/pf:check` if coverage looks good.

**With an aspect argument — deep-dive:**

Focus entirely on that one aspect. Read the canvas, show what's already there for that aspect, and go deep. Good for follow-up after a check reveals a specific gap.

**Questioning style:**

This is a conversation, not an interview. Adapt based on answers:
- If the user gives a short answer, ask a follow-up that goes deeper
- If they give a rich answer, extract the facts and move on
- If they seem uncertain, ask for examples or specifics
- If they're clearly done with a topic, move on — don't push
- Connect facts across aspects when you notice links: "You mentioned dental practitioners as users — does that shape who the customers are too?"

**Never say:** "Let's go through each aspect systematically" or "Question 3 of 8." This is not a checklist.

**Writes:** `products/<name>/canvas.md`
</objective>
