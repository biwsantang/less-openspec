# Artifact templates

Use these as structures, not filler. Remove unused optional sections and all
comments before finalizing an artifact.

## \`wiki/INSTRUCTIONS.md\`

\`\`\`markdown
# Wiki instructions

## Scope

Describe the product areas and repositories this wiki covers.

## Conventions

- Record current behaviour in \`wiki/specs/\`.
- Keep proposed behaviour in a named folder under \`wiki/changes/\`.

## Project-specific guidance

Add architecture, testing, release, or documentation constraints here.
\`\`\`

## \`proposal.md\`

\`\`\`markdown
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
\`\`\`

Use only the capability subsections that apply. For a change without
specification impact, write \`No specification change\` and explain why.

## \`design.md\`

\`\`\`markdown
# Design: <Change title>

## Context

## Goals and non-goals

## Decisions

## Risks and trade-offs

## Migration or rollback
\`\`\`

## \`tasks.md\`

\`\`\`markdown
# Tasks

## 1. <Area>

- [ ] 1.1 <focused work; verification: ...>

## 2. <Area>

- [ ] 2.1 <focused work; verification: ...>
\`\`\`

## Source spec

\`\`\`markdown
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
