# ADR-002: Independent Plugin, No Superpowers Dependency

**Date:** 2026-03-16
**Status:** Accepted

## Context

Superpowers provides brainstorming → spec → plan → execute pipeline. The PF plugin sits in a different domain (product thinking vs. engineering execution). The question was how they relate.

## Options Considered

**A. Independent** — Fully standalone. Handoff to engineering is manual.
**B. Complementary** — Independent but designed to hand off to superpowers (PRD formatted for writing-plans).
**C. Skill pack** — Ships as superpowers skills. Tighter integration but coupled.

## Decision

**Option A** — Fully independent.

## Rationale

The PF is product thinking, not engineering execution. The handoff from PRD to implementation is a human decision, not an automated pipeline. Keeping the plugin independent avoids coupling to superpowers' release cycle and conventions while keeping it usable by anyone.

## Consequences

- Plugin works for users who don't have superpowers installed
- PRD output is a standard markdown document, not formatted for any specific consumer
- Users who want to chain PF → superpowers can do so manually
