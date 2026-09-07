---
name: openspec-setup
description: Set up or migrate the repository-owned wiki used for Less OpenSpec. Use when the user asks to initialize spec-driven planning, set up OpenSpec-style artifacts, or migrate an existing openspec directory into wiki.
---

# Set up the wiki

Create a transparent, repository-owned planning space. This skill has no CLI or
runtime dependency.

Read [the shared artifact model](../references/artifact-model.md) and
[the templates](../references/templates.md) before making changes.

## New setup

Use this when \`wiki/\` does not exist and the user explicitly asks to set up
spec-driven planning.

1. Resolve the repository root and inspect its instructions, README, source
   layout, and tests.
2. Create only:

   \`\`\`text
   wiki/
   ├── INSTRUCTIONS.md
   ├── specs/
   └── changes/
       └── archive/
   \`\`\`

3. Write \`wiki/INSTRUCTIONS.md\` from the template, replacing placeholders
   with observed project scope and conventions. Keep it short and useful.
4. Do not create a configuration file, generated prompt, metadata file, hidden
   state directory, or empty change.
5. Report the created paths and the first useful next step:
   \`openspec-explore\` for an uncertain idea or \`openspec-propose\` for a
   ready change.

## Existing wiki

If \`wiki/\` already exists, inspect it and report its state. Do not overwrite
user-authored instructions or specs. Repair a missing conventional directory
only when the user asked to repair or initialize the wiki.

## Migration

If a legacy \`openspec/\` directory exists:

1. Inspect both roots and summarize the exact files that would move or copy.
2. Ask for explicit confirmation before changing either root.
3. On confirmation, preserve all Markdown and Git history by moving or copying
   the useful \`specs/\` and \`changes/\` content into \`wiki/\`.
4. Convert legacy configuration guidance into \`wiki/INSTRUCTIONS.md\` only
   when it is meaningful and clearly labelled as migrated guidance.
5. Never delete \`openspec/\` as an implicit side effect. Remove it only when
   the user explicitly requests removal after verifying the migration.
