# Less OpenSpec

Less OpenSpec is a skills-only implementation of spec-driven development for
Codex and Claude Code. It has no CLI, MCP server, hooks, generated command
files, global configuration, or hidden runtime state.

Install the plugin from this repository's marketplace. Then use one of the
bundled \`openspec-*\` skills in a coding-agent task.

## Project files

The skills keep planning artifacts in the project repository:

\`\`\`text
wiki/
├── INSTRUCTIONS.md
├── specs/
└── changes/
    └── archive/
\`\`\`

\`wiki/specs/\` is the source of truth for current behaviour. A proposed change
lives in \`wiki/changes/<change-name>/\`; after implementation, its delta specs
are reconciled with the main specs and the folder moves to
\`wiki/changes/archive/\`.

## Workflow

\`\`\`text
openspec-setup → openspec-explore → openspec-propose
                                      ↓
openspec-apply-change → openspec-verify-change → openspec-archive-change
                               ↘ openspec-update-change / openspec-sync-specs
\`\`\`

- \`openspec-setup\` creates the project-owned \`wiki/\` structure.
- \`openspec-propose\` writes proposal, optional design, delta specs, and tasks.
- \`openspec-apply-change\` implements checked work and updates task checkboxes.
- \`openspec-verify-change\` compares implementation with the change artifacts.
- \`openspec-sync-specs\` merges delta specs into the source specs.
- \`openspec-archive-change\` performs the final review, syncs when requested,
  and moves the completed change into the archive.

## Scope

This first release deliberately supports one repository and the built-in
spec-driven artifact model. Custom schemas, registered stores, dashboards,
shell completion, telemetry, and automatic cross-tool file generation were
CLI concerns and are intentionally not recreated.

See [the migration notes](docs/migration.md) and
[the artifact model](docs/artifact-model.md) for the durable format.
