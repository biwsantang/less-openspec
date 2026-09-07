# Shared artifact model

## Resolve the workspace

Work in the Git repository that contains the user's request. Resolve its root
before reading or writing. The plugin is local to that repository; do not look
for global stores or operate across repositories.

The only planning root is \`<repo>/wiki/\`:

\`\`\`text
wiki/
├── index.md                    # recommended OKF bundle index
├── INSTRUCTIONS.md
├── specs/
└── changes/
    └── archive/
\`\`\`

Read \`wiki/INSTRUCTIONS.md\` before every workflow. It is user-owned project
guidance. Preserve it and do not create hidden configuration or session files.

## OKF 0.2 contract

The wiki is an [Open Knowledge Format 0.2][okf] bundle. It remains ordinary
Markdown: no CLI, service, registry, hidden state, or schema tooling is needed.

- \`wiki/index.md\` is a reserved root index. When present, its front matter is
  exactly \`okf_version: "0.2"\`; it has no \`type\` or other metadata.
- \`wiki/log.md\`, if a project chooses to add one, is also reserved and has no
  concept front matter. Do not create it automatically; Git history is normally
  enough.
- Every other Markdown file under \`wiki/\`, including \`INSTRUCTIONS.md\`, is
  a concept. It needs parseable YAML front matter with a non-empty \`type\`.
- Use the recommended \`title\`, \`description\`, and \`tags\` when useful for
  discovery. Use \`status\` only as \`draft\`, \`stable\`, or \`deprecated\`.
- On a material skill-authored edit, update \`generated.by\` and
  \`generated.at\` (an ISO 8601 timestamp with an offset). Preserve unknown
  front-matter fields. Do not write legacy \`timestamp\`.
- Add \`sources\` only for artifacts genuinely consulted. Every source has a
  \`resource\`; give claim sources a stable \`id\` and cite it in the body as
  \`[^id]\`. A repository path may use the portable producer URI form
  \`repo://path/from/repository-root\`.
- Set \`verified\` only when the verifier has actual, reported evidence. It is
  never a guess, a synonym for generation, or an automatic archive marker.

The canonical types are: \`Repository Guidance\`, \`System Specification\`,
\`Change Proposal\`, \`Technical Design\`, \`Implementation Plan\`, and
\`Specification Delta\`. Type strings are descriptive rather than a closed
registry.

[okf]: https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md

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

When an active change becomes an archive, set every concept in that change to
\`status: deprecated\` before moving it. The documents remain usable historical
records; the status means they are no longer the current planning guidance.

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
- all non-reserved \`wiki/**/*.md\` files have parseable front matter and a
  non-empty \`type\`;
- root \`index.md\`, if present, contains only \`okf_version: "0.2"\`;
- every \`sources\` entry has \`resource\`, each cited \`[^id]\` matches a
  source id, and generated or verified timestamps are ISO 8601 values.

Report actual checks and limitations. Agent review is an evidence-based
workflow, not a claim of machine-enforced validation.
