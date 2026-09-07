---
name: openspec-archive-change
description: Finalize a completed change by reviewing it, syncing accepted delta specs, and moving it into wiki/changes/archive. Use when the user asks to archive or finalize a completed planned change.
---

# Archive a change

Read [the shared artifact model](../references/artifact-model.md) and
[the delta-spec rules](../references/delta-specs.md). Read
\`wiki/INSTRUCTIONS.md\` and select the active change using the shared rules.

1. Read all artifacts and count incomplete task checkboxes.
2. If tasks or required planning artifacts are incomplete, explain the risk and
   ask for explicit confirmation before archiving.
3. If delta specs exist, inspect whether their effects are already present in
   \`wiki/specs/\`. Summarize the result:
   - sync needed;
   - already synced; or
   - conflict requiring a decision.
4. When sync is needed, invoke the \`openspec-sync-specs\` procedure inline and
   verify its result before moving the change. Do not archive around a failed or
   unresolved sync.
5. Create the target name \`YYYY-MM-DD-<change-name>\`, using the current date
   unless the name already starts with that exact pattern. Confirm that the
   archive target does not exist.
6. Move the complete change directory to \`wiki/changes/archive/<target>/\`.
7. Report the archived path, sync result, validation evidence, and any
   user-approved warnings.

The archive is a move of user-owned Markdown, not deletion or hidden
finalization.
