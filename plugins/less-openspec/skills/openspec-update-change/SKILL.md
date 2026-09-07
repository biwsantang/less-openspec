---
name: openspec-update-change
description: Revise a planned change while keeping its proposal, specifications, design, and tasks coherent. Use when the user changes scope, makes a planning decision, or asks to update an existing change without implementing code.
---

# Update a planned change

This is a planning-only workflow. Edit files under the selected
\`wiki/changes/<change>/\` directory, not implementation code.

Read [the shared artifact model](../references/artifact-model.md),
[the templates](../references/templates.md), and
[the delta-spec rules](../references/delta-specs.md). Read
\`wiki/INSTRUCTIONS.md\` and select the active change using the shared rules.

1. Read every existing change artifact before editing.
2. Inspect relevant current source and tests when the requested revision depends
   on implementation facts.
3. Identify the source decision or new evidence, then update the smallest set
   of artifacts necessary to make the whole plan coherent.
4. Keep proposal scope, delta requirements, design decisions, and task
   verification aligned. Update task order when dependencies change.
5. Surface an ambiguity instead of silently selecting a product behaviour.
6. Re-read all artifacts and summarize the changed decisions, files, and
   remaining questions.

Do not mark implementation tasks complete and do not modify application code.
