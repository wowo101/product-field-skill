---
name: pf:import
description: Ingest existing material and map it onto a Product Field canvas
argument-hint: "<product-name> [path|glob]"
allowed-tools:
  - Read
  - Write
  - Glob
  - Grep
---

<context>
Product name: first argument (required)
Path/glob: second argument (optional — if omitted, scan the full repo)

@reference/model.md
@reference/aspects.md
</context>

<objective>
The brownfield onboarding ramp. Ingest scattered existing material and produce a structured PF canvas with clear gaps.

**Phase 1 — Ingest**

Gather all provided material. No limit on volume.
- No path argument → scan the repo tree for documents (markdown, docs, presentations, READMEs)
- Folder or file path → scan that location
- `@file` references → read those specific files
- Pasted text in conversation → process directly

Read everything before extracting. Build a mental model of the whole body of material first.

**Phase 2 — Extract**

Map content to PF aspects. For each extracted fact:
- Place it in the right aspect based on the definitions in aspects.md
- Tag it with epistemic status:
  - `[verified]` — measured, confirmed, evidenced in the material
  - `[observed]` — described as seen but not systematically measured
  - `[believed]` — stated as team consensus or assumption-presented-as-fact
  - `[assumed]` — implied but not explicitly stated
  - `[aspirational]` — described as a desired near-term state
  - `[visionary]` — described as a long-term direction

- Rank as Primary or Supporting based on emphasis in the source material

**Flag contradictions** — two sources claiming different values for the same variable within the same aspect. Example: one doc says "primary users are dentists," another says "primary users are procurement officers."

**Do NOT flag tensions** between different aspects. Tensions (GOALS want growth but ENABLERS are limited) are features, not bugs. Those get surfaced in Check.

**Phase 3 — Consolidate**

Walk through any flagged contradictions with the user. For each:
- Show the conflicting sources
- Ask the user to resolve: which is current, are both true (different segments), or is one outdated?
- Update the extraction based on their answers

**Phase 4 — Gap Report**

Generate a questionnaire for missing or thin aspects. For each gap:
- Which aspect is missing or thin
- Why it matters (which validation sentences depend on it)
- 2-3 specific questions to fill it
- Recommended method from methods.md if applicable

**Phase 5 — Write**

Create all output files:
- `products/<name>/canvas.md` — populated canvas from template
- `products/<name>/questionnaire.md` — the gap questionnaire
- `products/<name>/import-sources.md` — provenance log: what came from where
- Add to `backlog.md` if not already present

Report: summary of what was mapped, what's strong, what's thin, what's empty. Suggest `/pf:map <product-name>` to fill gaps or `/pf:check <product-name>` if coverage looks sufficient.

**Tone:** Analytical but not dry. You're making sense of scattered material — show the user the shape that emerges. Highlight surprises ("your material is rich on RESOURCES but says almost nothing about who the users are").
</objective>
