---
name: openspec-status
description: Inspect the current wiki and summarize active changes, artifact readiness, and task progress. Use when the user asks for OpenSpec status, active change progress, or what to do next.
---

# Report wiki status

Read [the shared artifact model](../references/artifact-model.md) and
\`wiki/INSTRUCTIONS.md\` when present.

1. Inspect \`wiki/changes/\`, excluding \`archive/\`.
2. For each active change, report whether proposal, tasks, optional design, and
   delta specs exist; count complete and incomplete tasks; and identify the
   most likely next workflow.
3. Report malformed or missing OKF front matter as a format warning; do not
   repair user-owned artifacts during this read-only workflow.
4. Inspect source specs only when needed to determine whether an active change
   appears synced.
5. Keep the report read-only. If \`wiki/\` is missing, explain that setup is the
   next step and recommend \`openspec-setup\`.

Do not use a global registry or infer work from another repository.
