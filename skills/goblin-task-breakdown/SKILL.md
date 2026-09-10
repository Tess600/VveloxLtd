---
name: goblin-task-breakdown
description: Convert vague, complex, overwhelming, or blocked work into an executable, dependency-ordered task graph with adjustable granularity. Use for task breakdowns, brain-dump compilation, next-action planning, stuck-state recovery, or machine-readable plans for Mentiad and Vulpes Velox.
---

# Goblin Task Breakdown

Turn a stated goal or brain dump into work a person can actually begin. Preserve the user's intended outcome, constraints, confirmed decisions, completed work, and task IDs.

This skill is inspired by Goblin Tools' approachable task decomposition but is independent and unaffiliated. Its distinguishing contract is: compile without overcommitting, decompose without losing intent, render without overwhelming, and execute without exceeding authorization.

## Choose a mode

- `task`: decompose one stated objective.
- `brain_dump`: extract candidate actions, decisions, worries, ideas, and reference information before decomposition.

Infer optional controls when clear:

- `granularity`: 1–5; default 3. Accept `spiciness` as an alias.
- `current_energy`: low, medium, or high.
- `available_time_min`: approximate usable time.
- `output_format`: human, json, or task_graph.
- `consumer`: human, mentiad, vulpes_velox, or external.

Ask at most one question, and only when its answer would materially change the first action. Otherwise state the smallest reasonable assumption and continue.

## Preserve canonical intent

Identify the outcome, observable definition of done, starting state, constraints, confirmed decisions, and completed work. Do not invent deadlines, access, people, requirements, commitments, or authorization.

When revising or resuming, preserve stable node IDs, completed nodes, and unrelated branches. Granularity changes presentation depth, not the goal.

## Compile brain dumps carefully

Separate content into actionable work, decisions, waiting items, ideas for later, and non-actionable context. Do not convert every sentence into a commitment. Mark inferred work as `proposed`; require confirmation before adding it to the canonical graph.

## Build executable nodes

Use one node type: `action`, `decision`, `wait`, `handoff`, or `checkpoint`.

An action node is executable only when it:

1. Starts with a concrete verb and acts on one identifiable object.
2. Names the tool, file, place, or person when known.
3. Has an observable completion condition.
4. Fits one focused sitting at the selected granularity.
5. Contains no hidden decision, wait, unresolved dependency, or multiple actions joined by “and.”
6. Requires no additional planning before it can begin.

Avoid vague verbs such as “handle,” “work on,” “figure out,” “prepare,” and “make progress.” Add setup or cleanup only when it removes real friction or protects project state.

## Granularity and friction

- 1: phases
- 2: coarse actions
- 3: executable actions, commonly 2–15 minutes
- 4: micro-actions
- 5: immediate steps for overload or panic

Track friction separately from granularity, duration, and energy. A short social or irreversible task can have high friction. When friction is high, expose fewer nodes, separate choices from actions, reduce context switching, and prefer a visible first result.

## Status and dependency rules

Use `proposed`, `ready`, `blocked`, `waiting`, `in_progress`, `done`, or `skipped`. A node is `ready` only when all dependencies are complete and no access or decision blocker remains. The graph must be acyclic, and `first_action_id` must reference a ready leaf node.

## Execution safety

Every machine-readable node records:

- `execution`: manual, agent, or either
- `side_effect`: none, read, write, external, or destructive
- `requires_approval`: true or false

Planning does not authorize execution. An agent may execute a node only when its status, dependencies, access, side effect, approval state, and active environment all permit it. Stop before communication, payment, publication, deletion, credential use, or another consequential action unless the user has authorized it.

## Produce the output

For people, progressively disclose:

1. Goal
2. Done means
3. Do now — exactly one smallest useful action
4. Next — at most three dependency-ordered actions
5. Blocked or waiting
6. Later

When overwhelmed, show exactly one 2–10 minute action and state what can safely wait.

For `json` or `task_graph`, read and conform to [`references/task-graph-schema.json`](references/task-graph-schema.json). Return valid JSON without commentary or Markdown fences when machine-only output is requested.

## Graph operations

- `expand <id>`: add child nodes while retaining the node as parent.
- `collapse <id>`: hide descendants without deleting them.
- `smaller <id>` / `bigger <id>`: change only that branch's granularity.
- `complete <id>`: mark done and release eligible dependents.
- `skip <id>`: preserve but remove from the active route.
- `resume`: return the next ready leaf.
- `recompile`: reassess proposed work without overwriting confirmed state.

Never regenerate unrelated branches.

## Consumer behavior

- Mentiad renders and preserves the canonical graph.
- Vulpes Velox receives only ready, authorized executable leaves.
- External adapters may flatten presentation but must preserve canonical meaning and report information loss.

Before returning, verify the observable definition of done, canonical intent, stable IDs, completed work, dependency order, immediate startability, valid machine output, and authorization boundaries.

