---
name: checkpointsave
description: Use at the start and end of coding, review, refactor, architecture, debugging, project-rule, or other important tasks in any workspace. At task start, read existing ./workCheckpoint/Rules/ and ./workCheckpoint/Works/ records when this is the first important task in the current workspace or when workspace memory is unavailable. At the end of a substantial or overall body of work, or a meaningful work stage, save consolidated, concise rule or work checkpoints under ./workCheckpoint/, including the current objective's construction strategy, completed objectives, next objectives, and any necessary closing notes. Avoid creating a checkpoint for every minor change so the workspace does not accumulate many low-content records.
license: MIT
---

# CheckpointSave

## Mandatory Startup Check

Before answering or editing for any coding, review, refactor, architecture, debugging, project-rule, or other important workspace task:

Read or modify files using UTF-8 encoding.

1. If this is the first important task in the current workspace, or workspace memory is unavailable, read this skill first.
2. Read all existing Markdown files under `./workCheckpoint/Rules/` if the directory exists.
3. Read all existing Markdown files under `./workCheckpoint/Works/` if the directory exists.
4. Treat those records as active workspace context before continuing.
5. If the directories do not exist, continue without creating them unless a checkpoint must be saved later.

## 1. Record Work

- Saving rules: Whenever the user provides important information with a long-term impact on the project, such as coding standards, project architecture, file structure, file or folder naming conventions, variable naming conventions, workflows, or other rules, record it in the directory specified below. Keep the record as brief as possible while preserving its core meaning.
- Saving work records: Record the operation process and key points only after a substantial or overall body of work, or a meaningful work stage, is complete. Consolidate related changes into one concise checkpoint instead of creating a separate file after every minor change. Also record the current objective's construction strategy, completed objectives, and next objectives when they help resume work after an interruption or support handoff. Keep all saved information as concise and focused as possible. Report in the response: "Checkpoint recorded."
- Saving rules: Use Chinese to record work rules.
- Saving work records: Use Chinese to record work records.

File saving rules:

- The document format is `.md`.
- Markdown escape characters are allowed.
- The file name must be "current date (accurate to the minute) + operation focus".

- Saving rules: Save documents under the `./workCheckpoint/Rules/` path in the current working directory. If this folder does not exist, it may be created. If work rule records were previously saved in the root directory, move them into this folder.
- Saving work records: Save documents under the `./workCheckpoint/Works/` path in the current working directory. If this folder does not exist, it may be created. If work records were previously saved in the root directory, move them into this folder.

## 2. Automatic Trigger at Task Start

If workspace memory is unavailable, or if this is the first coding, review, or other important task in the current conversation and you have not yet read the work rules (`workCheckpoint\Rules`) or work records (`workCheckpoint\Works`), read and remember those records. This is important.

## 3. Automatic Trigger at Task End

At the end of a substantial or overall task, or a meaningful work stage, automatically use this skill if any of the following conditions are met:

- New source code files or modules were created.
- Three or more project files were modified.
- A feature, subsystem, command, database or storage structure, or persistent data format was added.
- Compilation, build, or runtime integration logic was modified, such as includes, callbacks, routes, migrations, or configuration.
- The user explicitly emphasized future maintenance, handoff, coding, project conventions, or "record/remember/checkpoint".
- The task included non-obvious reasoning, important constraints that were discovered, or notes that need to be preserved.

Do not use this skill automatically in the following cases:

- Pure question answering with no file changes.
- A very small single-file fix.
- Formatting-only changes.
- A temporary experiment that was ultimately reverted.

When triggered automatically, save the checkpoint before the final response and briefly state the checkpoint path in the final response.

- For coding tasks, before the final response, check how many files were modified in this task and whether any modules or persistent formats were added.
- If the completed work is substantial or represents a meaningful stage and meets a trigger above, create the checkpoint directly without asking.
- When saving a task-end checkpoint, include closing notes when they help future continuation or handoff.
- When saving a task-end checkpoint, include the current objective's construction strategy, completed objectives, and next objectives when they help resume work after an interruption or support handoff.
