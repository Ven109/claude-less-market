# Spec-Driven Dev

A Claude Code plugin that guides you from idea to implementation through a structured, spec-driven workflow.

## The Workflow

```
/ideation → /tech-spec → /sprint-planning → /task-breakdown → /implement
```

Each step builds on the previous one, producing spec files that serve as the shared context for all subsequent steps.

### 1. `/ideation [idea or problem]`

Brainstorm complete solution approaches for a product idea or feature. Produces 3-5 cohesive concepts, helps you pick the right one, and saves the result.

**Output:** `specs/PROJECT.md`, `specs/ROADMAP.md`

### 2. `/tech-spec`

Define the technical architecture, stack, data models, and key design decisions. Includes project setup requirements for the first cycle.

**Output:** `specs/TECH_SPEC.md`

### 3. `/sprint-planning [cycle number]`

Break a roadmap phase into user stories with acceptance criteria and priorities.

**Output:** `specs/cycles/CYCLE_01.md`

### 4. `/task-breakdown [cycle number]`

Turn user stories into concrete, implementable tasks with dependencies and a suggested order.

**Output:** `specs/cycles/CYCLE_01_TASKS.md`

### 5. `/implement [cycle number]`

Work through the task list and build it. Checks off tasks as they're completed. Supports review mode (pause after each task) or continuous mode.

## Spec Structure

```
specs/
├── PROJECT.md              # Problem, chosen approach, key capabilities
├── ROADMAP.md              # Phased rollout plan (MVP → iterations → full vision)
├── TECH_SPEC.md            # Stack, architecture, data models, design decisions
└── cycles/
    ├── CYCLE_01.md          # User stories for cycle 1
    ├── CYCLE_01_TASKS.md    # Tasks with checkboxes for cycle 1
    ├── CYCLE_02.md
    └── CYCLE_02_TASKS.md
```

## Installation

```bash
claude --plugin-dir /path/to/claude-less-market/plugins/spec-driven-dev
```

## How It Works

Each skill is a structured prompt that guides Claude through a specific phase of the development process. The specs folder acts as persistent context — every step reads what came before and builds on it.

The workflow is sequential but flexible:

- You can re-run any step to iterate on its output
- You can skip steps if you already have the specs (e.g. start with `/sprint-planning` if you wrote PROJECT.md and ROADMAP.md yourself)
- Each step asks for confirmation before saving, so you stay in control
