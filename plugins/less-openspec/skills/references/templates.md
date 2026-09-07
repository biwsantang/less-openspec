# Artifact templates

Use these as structures, not filler. Remove unused optional sections and all
comments before finalizing an artifact.

## \`wiki/INSTRUCTIONS.md\`

\`\`\`markdown
---
type: Repository Guidance
title: Repository knowledge instructions
description: Rules for maintaining this repository's specifications and change records.
tags: [repository, guidance, openspec]
status: stable
generated:
  by: less-openspec/1.1.0
  at: <ISO 8601 timestamp with offset>
---

# Wiki instructions

## Scope

Describe the product areas and repositories this wiki covers.

## Conventions

- Record current behaviour in \`wiki/specs/\`.
- Keep proposed behaviour in a named folder under \`wiki/changes/\`.

## Project-specific guidance

Add architecture, testing, release, or documentation constraints here.
\`\`\`

## \`wiki/index.md\`

\`\`\`markdown
---
okf_version: "0.2"
---

# Repository knowledge

- [Repository guidance](INSTRUCTIONS.md)
- [<Capability>](specs/<capability>/spec.md)
\`\`\`

Do not add concept fields to this reserved root index.

## \`proposal.md\`

\`\`\`markdown
---
type: Change Proposal
title: <Change title>
description: <Retrieval-oriented summary of the change and its intent.>
tags: [<stable tag>]
status: draft
generated:
  by: less-openspec/1.1.0
  at: <ISO 8601 timestamp with offset>
sources:
  - id: <evidence-id>
    resource: repo://<path-from-repository-root>
    title: <Source title>
---

# <Change title>

## Why

## What changes

## Capabilities

### Added

- \`<capability-path>\`: <brief description>

### Modified

- \`<capability-path>\`: <brief description>

### Removed

- \`<capability-path>\`: <brief description>

## Impact

- Code:
- APIs:
- Dependencies:
- Risks:

[^<evidence-id>]: <The precise supported claim.>
\`\`\`

Use only the capability subsections that apply. For a change without
specification impact, write \`No specification change\` and explain why.
Remove \`sources\` and its footnote when no actual source was consulted.

## \`design.md\`

\`\`\`markdown
---
type: Technical Design
title: <Change title> design
description: <Technical decisions and trade-offs for the change.>
tags: [<stable tag>]
status: draft
generated:
  by: less-openspec/1.1.0
  at: <ISO 8601 timestamp with offset>
---

# Design: <Change title>

## Context

## Goals and non-goals

## Decisions

## Risks and trade-offs

## Migration or rollback
\`\`\`

## \`tasks.md\`

\`\`\`markdown
---
type: Implementation Plan
title: <Change title> implementation plan
description: Ordered and verifiable work needed to deliver the change.
tags: [<stable tag>]
status: draft
generated:
  by: less-openspec/1.1.0
  at: <ISO 8601 timestamp with offset>
---

# Tasks

## 1. <Area>

- [ ] 1.1 <focused work; verification: ...>

## 2. <Area>

- [ ] 2.1 <focused work; verification: ...>
\`\`\`

## Source spec

\`\`\`markdown
---
type: System Specification
title: <Capability>
description: <Current, accepted behavior for this capability.>
tags: [<stable tag>]
status: stable
generated:
  by: less-openspec/1.1.0
  at: <ISO 8601 timestamp with offset>
---

# <Capability>

## Purpose

<One or two sentences explaining current behaviour.>

## Requirements

### Requirement: <name>

<Normative, testable behaviour.>

#### Scenario: <name>

- **GIVEN** <precondition>
- **WHEN** <action or event>
- **THEN** <observable result>
\`\`\`

Read [\`delta-specs.md\`](delta-specs.md) for a change-local delta template.

## Metadata update rules

Keep front matter valid YAML. On an edit, update only the relevant provenance
fields and preserve unknown keys. Never add fake sources, verification, dates,
or placeholders to a finished document.
