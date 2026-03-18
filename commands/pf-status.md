---
name: pf:status
description: Portfolio dashboard — read-only view of all products
argument-hint: ""
---

<objective>
Show the current state of all products in the portfolio. Read-only — this command doesn't write anything.

**Steps:**

1. **Scan for products.** Look for `products/*/canvas.md`. Each directory with a canvas is a product.

2. **For each product, check what exists:**
   - `canvas.md` → has canvas
   - `questionnaire.md` → has questionnaire (from import)
   - `check.md` → has been checked
   - `find.md` → has been evaluated
   - `prd.md` → has PRD

3. **Assess canvas coverage.** For each product with a canvas:
   - Count aspects with primary facts vs. empty aspects
   - Note the overall epistemic quality — mostly verified? mostly assumed?
   - Identify the strongest and weakest corners

4. **Flag inconsistencies:**
   - PRD without check or find → requirements may be unvalidated
   - Check is older than canvas → canvas has been updated since last check
   - Empty aspects in critical positions (problem, solution, USERS)

5. **Display as a dashboard table:**

   ```
   Product     | Canvas | Check | Find | PRD | Coverage | Notes
   ------------|--------|-------|------|-----|----------|------
   showroom    | ✓      | ✓     | ✓    | —   | 10/12    | Ready for PRD
   data-api    | ✓      | —     | —    | —   | 5/12     | VALUE corner empty
   ```

6. **Suggest next action per product.** Based on what exists and what's missing:
   - No canvas → `/pf:new` or `/pf:import`
   - Canvas with gaps → `/pf:map`
   - Canvas filled → `/pf:check`
   - Check done → `/pf:find`
   - Find done → `/pf:prd`

7. **Show backlog if it exists.** Read `backlog.md` and display the top items.

**Writes:** nothing (read-only)
</objective>
