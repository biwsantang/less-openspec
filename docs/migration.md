# Migrating from OpenSpec

Less OpenSpec is not a drop-in replacement for the OpenSpec CLI. It keeps the
useful repository artifacts but replaces the CLI-owned workflow with plugin
skills.

## Preserve

- Existing proposal, design, task, and spec Markdown.
- Existing Git history.
- The distinction between source specs and per-change delta specs.

## Move to the new root

Do this through \`openspec-setup\` in a coding-agent task. It will inspect an
existing \`openspec/\` directory, explain the proposed mapping, and wait for
approval before moving or copying it to \`wiki/\`. It must not delete the source
directory as an implicit setup action.

## Not carried forward

- \`openspec\` executable, package publishing, and shell completion.
- Generated skills and slash commands for individual agent products.
- Global config, profiles, registered stores, worksets, and custom schemas.
- Dashboard, telemetry, GitHub Copilot cloud agent setup, and CLI validators.

The plugin itself is the installation mechanism. The skills inspect visible
Markdown and repository files directly, so a user can understand and edit the
entire workflow without a hidden runtime.
