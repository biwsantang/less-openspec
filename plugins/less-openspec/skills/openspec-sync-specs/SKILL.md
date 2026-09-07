---
name: openspec-sync-specs
description: Reconcile a change's delta specifications with the source specifications in wiki/specs. Use when the user wants to merge accepted requirements into the current specification without necessarily archiving the change.
---

# Sync delta specs

Read [the shared artifact model](../references/artifact-model.md) and
[the delta-spec rules](../references/delta-specs.md). Read
\`wiki/INSTRUCTIONS.md\` and select the active change using the shared rules.

1. Read every delta spec and corresponding source spec in full.
2. Present the additions, modifications, removals, and renames that will be
   applied. Ask before proceeding when a named existing requirement is missing,
   a change conflicts with the source spec, or a merge would lose an existing
   scenario.
3. Apply the delta exactly as described in the sync procedure:
   additions are added, modifications replace the whole requirement, removals
   remove only the named requirement, and renames preserve content unless also
   modified.
4. Re-read every source spec and verify the resulting content reflects each
   delta section once and only once.
5. Do not edit or delete the delta specs. They remain evidence until archive.

Report the source specs changed, requirements reconciled, and any unresolved
conflict. This skill does not archive the change.
