# Bridge to mosesliao/claude-skills

[`mosesliao/claude-skills`](https://github.com/mosesliao/claude-skills) and the Vulpes Velox Skills Suite use the same portable unit: a named folder containing `SKILL.md` and optional supporting directories.

## Relationship

- V.velox Ltd. maintains the canonical `goblin-task-breakdown` source and task-graph schema.
- Moses Liao maintains his independent skill collection.
- Neither repository is a dependency, fork, or ownership parent of the other.
- Cross-publication should use a pull request or an explicit copied release, retaining license and notice files.

## Contribution path

To propose this skill to Moses's collection:

1. Copy the complete `goblin-task-breakdown/` folder to the top level of a fork of `mosesliao/claude-skills`.
2. Retain `LICENSE` and `NOTICE.md` inside the copied folder because the destination repository is MIT-licensed while this skill is Apache-2.0-licensed.
3. Open a pull request explaining that V.velox Ltd. remains the canonical upstream.
4. Link the accepted location back here and record the source version or commit.

Do not automate bidirectional synchronization until both maintainers agree on versioning and conflict ownership.

