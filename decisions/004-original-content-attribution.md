# ADR-004: Original Content With CC BY-SA Attribution

**Date:** 2026-03-16
**Status:** Accepted

## Context

The Product Field Reference Guide is CC BY-NC-ND 4.0 (no derivatives, non-commercial). The Product Field model itself (the geographic structure) is CC BY-SA 4.0 (share-alike, derivatives OK). We needed to determine the IP approach for plugin content.

## Decision

Plugin reference files contain original content — our own descriptions, guiding questions, and method mappings. We use the model structure (aspect names, positions, relations) under CC BY-SA 4.0 with proper attribution. The reference guide PDF stays in .gitignored `literature/` for authoring use only.

## Context: Author Relationship

Mark knows the PF authors personally and is discussing this Claude Code integration with Wolfgang Wopperer-Beholz. The technical approach is clean regardless, but the relationship opens the door for deeper collaboration (official endorsement, co-branding) in the future.

## Consequences

- All distributed content is original and properly attributed
- The PF authors can review and potentially contribute
- Future official collaboration is architecturally possible without restructuring
