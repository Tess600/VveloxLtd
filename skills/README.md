# Vulpes Velox Skills Suite

Open-source consulting aides from V.velox Ltd. Each skill turns a repeatable consulting method into a portable instruction set with explicit inputs, outputs, and safety boundaries.

## Skills

| Skill | Purpose | Status |
|---|---|---|
| [`goblin-task-breakdown`](./goblin-task-breakdown/) | Turns vague, blocked, or overwhelming work into a stable, dependency-ordered task graph | Experimental |

## Installation

Copy a skill folder into one of these locations:

- Project: `.claude/skills/<skill-name>/`
- Personal: `~/.claude/skills/<skill-name>/`
- Upload/package workflows: use the complete skill folder as the portable unit

## Compatibility

Skills use the same portable folder contract as [mosesliao/claude-skills](https://github.com/mosesliao/claude-skills): a named directory containing `SKILL.md` plus optional `references/`, `examples/`, and `scripts/`.

The repositories remain independently owned. See the [Moses bridge note](./goblin-task-breakdown/adapters/moses-claude-skills.md) for the contribution and synchronization path.

