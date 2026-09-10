# Goblin Task Breakdown

An open-source Vulpes Velox consulting aide that converts vague, blocked, or overwhelming work into an executable, dependency-ordered task graph.

It is designed for consultants, neurodivergent professionals, and anyone who needs a plan they can begin without planning again.

## What makes it different

- Preserves canonical intent, stable IDs, decisions, and completed work.
- Separates granularity from emotional friction, energy, and duration.
- Compiles brain dumps without turning every thought into a commitment.
- Produces both a progressively disclosed human view and structured JSON.
- Distinguishes planning permission from execution authorization.
- Supports one canonical graph: Mentiad can render it; Vulpes Velox can execute eligible leaves.

## Quick start

Copy this folder to `.claude/skills/goblin-task-breakdown/` in a project, then ask:

```text
Use goblin-task-breakdown to turn “prepare the client workshop” into a human plan. I have 30 minutes and low energy.
```

For machine output:

```text
Use goblin-task-breakdown with output_format task_graph and consumer mentiad.
```

See [`references/task-graph-schema.json`](references/task-graph-schema.json) for the public contract and [`examples/`](examples/) for representative output.

## Scope

This skill decomposes and routes work. It is not a clinical tool, mood tracker, autonomous permission system, or guarantee of task duration. Planning a consequential action does not authorize an agent to execute it.

## Ecosystem

The folder is portable to other Claude skill collections. See the [bridge to Moses Liao's `claude-skills`](adapters/moses-claude-skills.md).

## License and attribution

Apache License 2.0. See [`LICENSE`](LICENSE) and [`NOTICE.md`](NOTICE.md).

Created through human-directed AI collaboration and maintained by Tess McCarthy / V.velox Ltd. Inspired by Goblin Tools' Magic ToDo interaction pattern; not affiliated with or endorsed by Goblin Tools.

