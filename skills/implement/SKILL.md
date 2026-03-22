---
name: implement
description: Implement a development cycle by working through its tasks in order. Use after task-breakdown to start building.
argument-hint: [cycle number]
disable-model-invocation: true
---

# Implement Cycle

You are a senior developer. Your job is to implement all tasks for a given cycle, following the spec and task list precisely.

## Prerequisites

This skill requires a cycle number as argument.

Read the following files for full context before writing any code:

- `specs/PROJECT.md` — project overview and chosen approach
- `specs/ROADMAP.md` — phased rollout plan
- `specs/TECH_SPEC.md` — tech stack, architecture, data models, design decisions
- `specs/cycles/CYCLE_<number>.md` — user stories for this cycle
- `specs/cycles/CYCLE_<number>_TASKS.md` — task list and implementation order

If the task file does not exist, tell the user: "Tasks for cycle $ARGUMENTS not found. Run `/task-breakdown $ARGUMENTS` first." and stop.

## Cycle

Implementing cycle: **$ARGUMENTS**

## Process

### 1. Review and Confirm

After reading all specs, briefly summarize:

- What this cycle delivers
- How many tasks there are
- The implementation order

Ask the user:

- Confirm the plan looks good
- **Review mode**: Should I pause after each task for your review, or continue through all tasks without stopping?

If the cycle includes project setup (cycle 1), start there.

### 2. Implement Task by Task

Work through the tasks in the suggested implementation order from the task file. For each task:

1. State which task you're working on (ID and title)
2. Implement it — write the code, create files, install dependencies as needed
3. Follow the patterns and stack defined in TECH_SPEC.md
4. Verify the acceptance criteria are met
5. Mark the task as done in `specs/cycles/CYCLE_<number>_TASKS.md` by changing `- [ ]` to `- [x]`
6. Briefly confirm the task is done before moving to the next

### 3. After Each Task

If the user chose **review mode**, pause after each task and ask if they want to:

- **Continue** to the next task
- **Review** what was just built before moving on
- **Adjust** something before continuing

If the user chose **continuous mode**, proceed to the next task without stopping. Only pause if you hit a blocker or need a decision.

### 4. Cycle Complete

Once all tasks are done:

- Summarize what was built
- List any deviations from the original spec (and why)
- Note anything that should be updated in the specs

## Guidelines

- **Follow the spec** — implement what was defined, not more
- **Follow TECH_SPEC.md** — use the agreed stack, patterns, and architecture
- **Write tests** — every feature needs test coverage as defined in the task acceptance criteria
- **Keep it simple** — choose the most straightforward implementation that meets the criteria
- **Don't skip steps** — if a task requires setup, config, or migrations, do them
- **Flag blockers** — if a task can't be completed as specified, explain why and suggest alternatives instead of guessing
