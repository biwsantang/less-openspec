# Shared artifact model

## Resolve the workspace

Work in the Git repository that contains the user's request. Resolve its root
before reading or writing. The plugin is local to that repository; do not look
for global stores or operate across repositories.

The only planning root is \`<repo>/wiki/\`:

\`\`\`text
wiki/
├── INSTRUCTIONS.md
├── specs/
└── changes/
    └── archive/
\`\`\`

Read \`wiki/INSTRUCTIONS.md\` before every workflow. It is user-owned project
guidance. Preserve it and do not create hidden configuration or session files.

## Change layout

\`\`\`text
wiki/changes/<change-name>/
├── proposal.md
├── design.md                       # optional
├── tasks.md
└── specs/<capability-path>/spec.md # one or more delta specs, optional
\`\`\`

Use lower-case kebab-case change names and capability path segments. Keep the
capability path stable when a current spec already exists.

The default flow is:

\`\`\`text
explore → propose → apply → verify → archive
                    ↕        ↕
                  update    sync
\`\`\`

Planning workflows may edit only \`wiki/\`. Apply is the only workflow that
edits implementation files. Archive may move a completed change inside
\`wiki/changes/\`.

## Artifact rules

### Proposal

Every proposal states why the change matters, what changes, affected
capabilities, and impact. It records assumptions rather than silently making
material product decisions.

### Delta specs

Delta specs describe changes to the accepted source specs in
\`wiki/specs/\`. Use the exact headings described in
[\`delta-specs.md\`](delta-specs.md). A refactor, tooling, or documentation-only
change can omit delta specs; say so explicitly in the proposal.

### Design

Create \`design.md\` only when the change needs a meaningful technical decision:
an architectural boundary, migration, security/performance trade-off, external
dependency, or unresolved implementation risk. Do not write a design just to
repeat the proposal or tasks.

### Tasks

Tasks use Markdown checkboxes and stable numbers:

\`\`\`markdown
## 1. Area

- [ ] 1.1 Do a focused unit of work and state how it will be verified
\`\`\`

Mark a task complete only after its full behaviour is implemented and verified.

## Selecting a change

When a workflow accepts an optional change name:

1. Use an explicit name.
2. Otherwise use an unambiguous active change from conversation context.
3. Otherwise inspect \`wiki/changes/\`, excluding \`archive/\`.
4. Auto-select only if exactly one active change exists.
5. Ask the user to choose when more than one remains.

## Validation checklist

Before reporting a workflow complete, check what applies:

- required files exist and use the templates;
- links and capability paths resolve;
- change name is safe and does not overwrite another active change;
- delta requirements have scenarios;
- task numbering is unique and task text contains verification;
- planning artifacts agree about scope;
- implementation changes are covered by completed task evidence;
- an archive target does not already exist.

Report actual checks and limitations. Agent review is an evidence-based
workflow, not a claim of machine-enforced validation.
