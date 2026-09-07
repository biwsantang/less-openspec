# Artifact model

Less OpenSpec keeps all durable state in ordinary Markdown under the current
repository's \`wiki/\` directory:

\`\`\`text
wiki/
├── index.md
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

The wiki follows OKF 0.2. `index.md` is the optional declared bundle index and
contains only `okf_version: "0.2"` in its YAML front matter. Every other
Markdown artifact is an OKF concept with a non-empty `type`; common optional
fields include `title`, `description`, `tags`, `sources`, `generated`,
`verified`, `status`, and `stale_after`. The skills preserve unknown metadata
and never create a runtime database to manage it.

Read the bundled skill reference
[\`artifact-model.md\`](../plugins/less-openspec/skills/references/artifact-model.md)
for the workflow rules and exact templates.
