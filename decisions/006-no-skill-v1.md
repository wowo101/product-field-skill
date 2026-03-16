# ADR-006: No Skill in v1, CLAUDE.md Handles Session Awareness

**Date:** 2026-03-16
**Status:** Accepted

## Context

A skill could provide ambient PF awareness during sessions — recognizing when conversation touches product topics and suggesting structured PF work. The question was whether this is needed in v1.

## Decision

No skill in v1. The product repo's CLAUDE.md provides session-level PF awareness. Skill deferred to v1.1 for gap-awareness functionality.

## Rationale

The product repo IS the PF context. Every session in it is product work by definition. The CLAUDE.md establishes PF as the operating vocabulary. A skill adds value for gap-awareness ("I know your canvases have gaps in DISTRIBUTION and I'm listening for content that fills them"), but this depends on having good canvases first — so commands come first.

## Consequences

- v1 is simpler (commands only)
- The CLAUDE.md snippet in `templates/claude-md-snippet.md` is the key onboarding artifact
- v1.1 skill can be added without changing anything else
