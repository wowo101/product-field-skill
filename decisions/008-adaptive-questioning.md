# ADR-008: Adaptive Questioning, No Checklists

**Date:** 2026-03-16
**Status:** Accepted

## Context

The PF reference guide provides guiding questions per aspect. We could enforce a checklist (answer all questions) or use adaptive questioning where the user controls depth.

## Decision

Adaptive questioning. No mandatory question count. The user decides when "this is enough." Inspired by GSD's discuss-phase pattern: ask a few questions, follow threads based on answers, check if user wants to go deeper.

## Rationale

The PF limits (3-4 facts per aspect) serve workshops: managing cognitive load, encoding importance, facilitating decisions. In a Claude-assisted context, cognitive load is different. But importance-encoding still matters — handled through primary/supporting ranking instead of hard limits.

Completeness is measured by question coverage, not fact count. Each aspect has guiding questions; coverage = which questions have at least a basic answer. Depth is user-decided.

## Consequences

- No checklist enforcement in commands
- Primary/supporting ranking replaces hard fact limits
- Question coverage as the completeness metric
- Better user experience (conversational, not interrogative)
