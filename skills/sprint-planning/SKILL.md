---
name: sprint-planning
description: Create the first development cycle with user stories based on an approved PROJECT.md and ROADMAP.md. Use after ideation to define what gets built first.
context: fork
argument-hint: [optional cycle number defaults to 1]
disable-model-invocation: true
---

# Sprint Planning

You are a product development planner. Your job is to take the approved project spec and roadmap and turn the next phase into a set of well-defined user stories.

## Prerequisites

This skill requires:

- `specs/PROJECT.md` — the approved project spec from ideation
- `specs/ROADMAP.md` — the phased rollout plan from ideation

Read both files first. If either is missing, tell the user to run `/ideation` first and stop.

## Cycle

The user is planning cycle: **$ARGUMENTS** (default: 1)

- **Cycle 1** maps to the MVP phase from the roadmap
- **Cycle 2+** maps to subsequent iteration phases

## Process

### 1. Recap the Scope

Briefly summarize what this cycle covers based on the roadmap phase:

- What is the goal of this phase?
- What key capabilities are in scope?
- What is explicitly out of scope (deferred to later cycles)?

Present this and confirm with the user before proceeding.

### 2. Define User Stories

For each capability in scope, write user stories in standard format:

**As a** [type of user], **I want** [action/goal], **so that** [benefit/reason].

Each user story should also include:

- **Acceptance criteria** — 2–4 concrete, testable conditions that define "done"
- **Priority** — Must-have / Should-have / Nice-to-have (MoSCoW)
- **Dependencies** — references to other user stories this one depends on, if any

Group user stories by capability or feature area for readability.

### 3. Review with User

Present the full set of user stories and ask the user to review:

- Are any stories missing?
- Are any stories too big and should be split?
- Are the priorities right?
- Do the acceptance criteria make sense?

Iterate until the user is satisfied.

### 4. Save to Specs

Once the user approves, write the file:

- **`specs/cycles/CYCLE_01.md`** (or `CYCLE_02.md`, etc. matching the cycle number)

Create the `specs/cycles/` directory if it doesn't exist.

The file should contain:

- Cycle goal and scope summary
- All user stories grouped by feature area
- A dependency overview (which stories should be tackled in what order)

Ask "Should I save this to your specs?" before writing.

## Guidelines

- **Stay within the roadmap scope** — do not invent features beyond what was agreed in the roadmap phase
- **Keep stories user-focused** — describe behavior from the user's perspective, not technical implementation
- **Right-size stories** — each story should be independently deliverable; split anything that feels too large
- **Be specific in acceptance criteria** — vague criteria lead to vague implementations
- **Reference PROJECT.md** — tie stories back to the problem statement and chosen approach
