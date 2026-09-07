---
name: openspec-propose
description: Create a complete spec-driven change proposal in wiki/changes. Use when the user wants to plan a feature, bug fix, refactor, or behaviour change before implementation.
---

# Propose a change

Create planning artifacts only. The request that invokes this skill does not
authorize implementation; stop after the proposal is ready.

Read [the shared artifact model](../references/artifact-model.md),
[the templates](../references/templates.md), and
[the delta-spec rules](../references/delta-specs.md). Read
\`wiki/INSTRUCTIONS.md\` when present. If no \`wiki/\` exists, ask the user to
run \`openspec-setup\` or explicitly authorize creating it.

1. Derive a lower-case kebab-case change name from the request. Ask only about
   ambiguity that materially changes behaviour, compatibility, scope, or
   acceptance criteria.
2. Ensure \`wiki/changes/<change-name>/\` does not already exist. If it does,
   offer to revise that change with \`openspec-update-change\`.
3. Inspect the affected code, tests, docs, and source specs before writing.
   Ground the plan in evidence; record material assumptions.
4. Create \`proposal.md\` with the \`Change Proposal\` OKF front matter.
   Record sources actually used for material claims; do not invent them.
5. Create one or more delta specs for changes to specified behaviour. If the
   work has no specification impact, state that explicitly in the proposal
   instead of inventing a capability. Each delta uses \`Specification Delta\`
   front matter.
6. Create \`design.md\` with \`Technical Design\` front matter only when a non-trivial technical decision or risk
   needs to be recorded.
7. Create \`tasks.md\` with \`Implementation Plan\` front matter and ordered,
   independently verifiable checkbox tasks.
8. Re-read all artifacts and check agreement on scope, capability paths, task
   ordering, and the shared OKF 0.2 contract.

Report the created files, key decisions, assumptions, and any question the
user should answer before implementation. End by directing the user to
\`openspec-apply-change\`.
