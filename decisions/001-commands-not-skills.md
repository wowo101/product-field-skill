# ADR-001: Commands + Reference Files, Not Skills

**Date:** 2026-03-16
**Status:** Accepted

## Context

Claude Code plugins can ship skills (behavioral modification, loaded on trigger), commands (explicit invocation), or both. We needed to decide how to package the Product Field framework.

## Options Considered

**A. Skills-based** — Each workflow step as a skill (loaded on demand). Reference files within skill directories.
- Pro: Follows official plugin pattern. Context-efficient.
- Con: Skills are designed for behavioral modification ("how to brainstorm"), not domain knowledge.

**B. Commands + reference files** — Commands as entry points, reference files loaded on demand via `@` references.
- Pro: Clean separation of behavior and knowledge. GSD proves this works. Reference files are independently valuable.
- Con: Not using official skill mechanism.

**C. Hybrid** — One always-on skill for PF awareness + commands for workflow steps.
- Pro: Bridges casual conversation into structured PF work.
- Con: Context cost for non-product sessions. More complex.

## Decision

**Option B** — Commands + reference files.

## Rationale

The PF is a domain framework ("here's a knowledge model and structured process"), not behavioral modification ("brainstorm before coding"). The product repo's CLAUDE.md provides session-level PF awareness — every session in a product repo is product work by definition, so no always-on skill is needed. Reference files as standalone markdown have value beyond Claude Code (documentation, review by PF authors, other AI tools).

## Consequences

- Commands explicitly load their needed context — no ambient overhead
- Reference files can be reviewed independently (valuable for collaboration with PF authors)
- Gap-awareness skill deferred to v1.1, when canvases exist to be aware of
