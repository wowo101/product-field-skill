# ADR-007: Epistemic Status Tags on Every Fact

**Date:** 2026-03-16
**Status:** Accepted

## Context

Facts mapped to a canvas aren't equal. Some are measured, some are assumptions, some are aspirations. Without marking this, a force field assessment treats beliefs as if they were verified truths.

## Decision

Every fact in the canvas gets an epistemic status tag: `[verified]`, `[observed]`, `[believed]`, `[assumed]`, `[aspirational]`, `[visionary]`. Aspirational/visionary items optionally include temporal horizon.

## Rationale

- A "strength" based on an assumption is a risk disguised as a strength
- The force field should weight by epistemic status
- Low-confidence primary facts are discovery priorities (connects to Torres' assumption testing)
- Tags make the team's actual knowledge vs. beliefs visible

## Consequences

- Canvas format is richer (each fact has a tag)
- `/pf:find` weights evaluation by confidence level
- Natural bridge to v1.1 `/pf:discover` command (assumption-testing plan from tags)
- Import command must assign epistemic status during extraction
