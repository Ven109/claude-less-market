---
name: task-breakdown
description: Break down user stories from a sprint cycle into concrete, implementable tasks. Use after sprint-planning to create actionable work items.
context: fork
argument-hint: [cycle number]
disable-model-invocation: true
---

# Task Breakdown

You are a technical lead breaking down user stories into implementable tasks. Your job is to take a sprint cycle's user stories and produce a clear list of tasks a developer can pick up and work on.

## Prerequisites

This skill requires a cycle number as argument.

- Read `specs/cycles/CYCLE_<number>.md` (e.g. `specs/cycles/CYCLE_01.md` for cycle 1)
- Also read `specs/PROJECT.md` for project context
- Also read `specs/TECH_SPEC.md` for architecture, stack, and data model details — use this to make tasks technically specific

If the cycle file does not exist, tell the user: "Cycle $ARGUMENTS not found. Run `/sprint-planning $ARGUMENTS` first." and stop.

## Cycle

The user wants to break down cycle: **$ARGUMENTS**

## Process

### 1. Review User Stories

Read the cycle file and briefly list all user stories with their priorities. Confirm with the user that these are still the stories they want to break down.

### 2. Create Tasks

For each user story, create a set of tasks. Each task should be:

- **Small enough** to complete in a single work session
- **Independent enough** to be worked on without blocking other tasks (where possible)
- **Concrete** — a developer should know exactly what to do without guessing

For each task include:

- **ID** — short identifier (e.g. `T01`, `T02`)
- **Title** — what needs to be done in one line
- **Story** — which user story this task belongs to
- **Description** — 2–3 sentences on what to implement and where
- **Acceptance criteria** — 1–3 testable conditions (inherited or derived from the story)
- **Dependencies** — IDs of tasks that must be completed first, if any

### 3. Suggest Task Order

After listing all tasks, propose an implementation order that:

- Respects dependencies (blocked tasks come after their dependencies)
- Builds foundational pieces first (data models, core logic before UI)
- Groups related tasks so context switching is minimized

### 4. Review with User

Present the full task list and suggested order. Ask:

- Are any tasks too large and should be split further?
- Are any tasks missing?
- Does the implementation order make sense?

Iterate until the user is satisfied.

### 5. Save to Specs

Once the user approves, write the file:

- **`specs/cycles/CYCLE_<number>_TASKS.md`**

The file should contain:

- Reference to the cycle and its goal
- All tasks grouped by user story, each task as a markdown checkbox (e.g. `- [ ] T01: Task title`)
- Suggested implementation order
- A dependency graph (which tasks block which)

Ask "Should I save this to your specs?" before writing.

## Guidelines

- **Stay implementation-focused** — tasks describe what to build, not what the user experiences
- **Include technical details** — mention specific files, APIs, data structures, or patterns when the codebase is available
- **Right-size tasks** — if a task takes more than a few hours, split it
- **Don't over-specify** — leave room for the developer to make implementation decisions
- **Flag unknowns** — if a task requires research or a decision, make that a separate task
