---
name: openspec-apply-change
description: Implement the checked work from a planned change in wiki/changes. Use when the user asks to start or continue implementing an OpenSpec-style change or to work through its task list.
---

# Apply a planned change

Read [the shared artifact model](../references/artifact-model.md). Read
\`wiki/INSTRUCTIONS.md\` and select the change using the shared selection rules.

1. Read \`proposal.md\`, all delta specs, \`design.md\` when present, and
   \`tasks.md\` before editing code.
2. Report the selected change, current task progress, and the first task to be
   worked on.
3. Implement pending tasks in dependency order. Keep each code change focused
   on the selected task and use the project's existing test and style
   conventions.
4. Run the verification stated in the task where possible.
5. Change a task from \`- [ ]\` to \`- [x]\` only after the specified behaviour
   is fully implemented and verified.
6. Pause and ask the user when a task is unclear, a material design conflict is
   found, scope must change, or validation exposes an unresolved problem.

On completion or pause, report completed tasks, verification evidence, remaining
work, and the appropriate next skill. Recommend \`openspec-verify-change\`
when all tasks are complete.
