# Delta specs and syncing

A change-local spec at
\`wiki/changes/<change>/specs/<capability>/spec.md\` is a delta against
\`wiki/specs/<capability>/spec.md\`.

\`\`\`markdown
# Delta: <Capability>

## ADDED Requirements

### Requirement: <name>

<New normative behaviour.>

#### Scenario: <name>

- **GIVEN** <precondition>
- **WHEN** <event>
- **THEN** <outcome>

## MODIFIED Requirements

### Requirement: <existing name>

<The complete replacement requirement, including retained scenarios.>

#### Scenario: <name>

- **GIVEN** <precondition>
- **WHEN** <event>
- **THEN** <outcome>

## REMOVED Requirements

### Requirement: <existing name>

<Why the behaviour is removed.>

## RENAMED Requirements

- \`<old name>\` → \`<new name>\`
\`\`\`

Include only headings that apply.

## Sync procedure

1. Read the delta and the current main spec in full.
2. Summarize every planned addition, replacement, removal, and rename.
3. Stop for clarification if a modified or removed requirement cannot be found,
   a rename collides, or the delta would discard scenarios that should remain.
4. For additions, add the full requirement and scenarios to the main spec.
5. For modifications, replace the entire named requirement with the complete
   delta version. Do not append a second requirement of the same name.
6. For removals, remove only the named requirement.
7. For renames, preserve the requirement body and scenarios while changing its
   name, unless the delta also modifies it.
8. Re-read the main spec and confirm every delta section has been reflected.

Do not modify the delta during sync. It is preserved as historical evidence
inside the archived change.
