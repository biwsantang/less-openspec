# Artifact model

Less OpenSpec keeps all durable state in ordinary Markdown under the current
repository's \`wiki/\` directory:

\`\`\`text
wiki/
├── INSTRUCTIONS.md
├── specs/<capability>/spec.md
└── changes/
    ├── <change-name>/
    │   ├── proposal.md
    │   ├── design.md                 # only when technical decisions need it
    │   ├── tasks.md
    │   └── specs/<capability>/spec.md
    └── archive/YYYY-MM-DD-<change-name>/
\`\`\`

The main specs describe current, accepted behaviour. A change's specs are
deltas: they say what to add, modify, remove, or rename. The archive is an
audit trail, not a cache.

There is no \`config.yaml\`, change metadata file, generated agent prompt,
session record, or global store registry. Put durable project constraints in
\`wiki/INSTRUCTIONS.md\`.

Read the bundled skill reference
[\`artifact-model.md\`](../plugins/less-openspec/skills/references/artifact-model.md)
for the workflow rules and exact templates.
