---
name: pf:new
description: Create a new product canvas and register it in the backlog
argument-hint: "<product-name>"
---

<context>
Product name: $ARGUMENTS (required — kebab-case, e.g. "data-api" or "showroom")

@reference/model.md
</context>

<objective>
Create a new Product Field canvas for the given product and get the user started with a few framing questions.

**Steps:**

1. **Validate input.** The product name is required. If missing, ask for it. Use kebab-case for the directory name.

2. **Check for existing canvas.** Look for `products/<product-name>/canvas.md`. If it exists, tell the user and ask if they want to start fresh (overwrite) or use `/pf:map` to continue filling it in.

3. **Create the canvas.** Copy the canvas template into `products/<product-name>/canvas.md`. Replace `[PRODUCT NAME]` with the product name (title case).

4. **Add to backlog.** If `backlog.md` exists, add a line: `- Map: <product-name> canvas [new]`. If it doesn't exist, create it with a header and the first item.

5. **Ask framing questions.** Have a brief conversation to pre-fill the center and the most obvious aspects. Ask 3-4 questions, one at a time:
   - "What is [product-name] in one sentence?" → fills Center
   - "Who is it for?" → gives a starting point for USERS
   - "What problem does it solve for them?" → starting point for problem
   - "What's the organizational goal behind it — why build this?" → starting point for GOALS

   Tag all answers `[believed]` unless the user indicates stronger evidence. Place facts as Primary. Don't force all questions — if the user has already given context, skip what's already covered.

6. **Report.** Show which aspects now have content and which are still empty. Suggest `/pf:map <product-name>` as the next step, or `/pf:import <product-name>` if they have existing material to bring in.

**Tone:** Conversational, not interrogative. This is the first touch — make it feel like a natural conversation, not a form to fill out.

**Writes:** `products/<name>/canvas.md`, `backlog.md`
</objective>
