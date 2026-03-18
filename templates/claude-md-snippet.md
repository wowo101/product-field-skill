# Product Field — CLAUDE.md Snippet

_Copy the section below into your products repo's CLAUDE.md to enable PF-aware sessions._

---

## Product Thinking

This repo uses the [Product Field](https://productfield.com) framework for product thinking. Product canvases, validation checks, and evaluations live in `products/<product-name>/`.

### How product work happens here

Every session in this repo is product work. When discussing products, use PF vocabulary:
- **Aspects:** GOALS, DRIVERS, ENABLERS, PRODUCTION, DISTRIBUTION, CUSTOMERS, USERS, MOTIVATIONS (context) + problem, solution, uniqueness, alternatives (core)
- **Corners:** IDEA (inside+purpose), VALUE (outside+purpose), RESOURCES (inside+implementation), MARKET (outside+implementation)
- **Workflow:** Map → Check → Find → PRD

### Key files per product

- `canvas.md` — the 12 aspects mapped by quadrant, facts tagged with epistemic status
- `check.md` — validation: 4 sentence templates testing core/context fit
- `find.md` — evaluation: strengths/weaknesses, force field, character type
- `prd.md` — product requirements derived from validated canvas
- `questionnaire.md` — gap questionnaire from import

### Epistemic status tags

Every fact in a canvas is tagged: `[verified]`, `[observed]`, `[believed]`, `[assumed]`, `[aspirational]`, `[visionary]`. Low-confidence primary facts are discovery priorities.

### Commands

Use `/pf:status` to see the state of all products. Use `/pf:map <product>` to fill in a canvas. Use `/pf:check <product>` to validate. See the product-field plugin for all commands.
