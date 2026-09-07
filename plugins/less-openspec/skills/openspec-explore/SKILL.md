---
name: openspec-explore
description: Explore an idea, bug, or design question before committing to a change. Use when the user wants to investigate options, clarify requirements, or think through a possible change without yet creating planning artifacts.
---

# Explore before proposing

Help the user decide what should be changed without creating a change folder or
editing implementation.

Read [the shared artifact model](../references/artifact-model.md). If
\`wiki/INSTRUCTIONS.md\` exists, read it before research.

1. Ask for a topic only when the user's goal is genuinely unclear.
2. Inspect relevant code, tests, documentation, and current \`wiki/specs/\`.
3. Separate observed facts, unknowns, assumptions, and alternatives.
4. Compare options by user-visible behaviour, compatibility, effort, and risk.
5. Recommend a next step:
   - \`openspec-propose\` when the scope is ready;
   - more investigation when a material uncertainty remains; or
   - no change when the evidence does not justify one.

Keep this discussion non-destructive. Do not create \`wiki/changes/\` content,
modify specs, or implement code unless the user makes a separate explicit
request.
