---
name: openspec-verify-change
description: Verify that implementation satisfies a planned change before archive. Use when the user asks to review completion, validate a change against its artifacts, or prepare a change for archiving.
---

# Verify a change

Read [the shared artifact model](../references/artifact-model.md). Read
\`wiki/INSTRUCTIONS.md\` and select the active change using the shared rules.

1. Read the proposal, delta specs, optional design, and tasks in full.
2. Inspect implementation and tests against every requirement and task.
3. Run the relevant existing checks where practical. Distinguish checks actually
   run from review-only evidence.
4. Report findings grouped as:
   - satisfied;
   - incomplete or unverified;
   - specification or design mismatch; and
   - unrelated observations.
5. Mark a task complete only when the evidence supports it. Do not silently
   change requirements to match incomplete implementation.
6. When the user asks to record a successful verification, add or update the
   relevant artifact's \`verified: { by, at }\` only after reporting the exact
   supporting checks. Preserve unknown metadata and never record verification
   for review-only or incomplete evidence.
7. If the change is ready, say so and recommend \`openspec-archive-change\`.
   Otherwise recommend the smallest appropriate follow-up: apply, update, or
   sync.

Do not archive, move change folders, or make broad implementation edits as part
of verification.
