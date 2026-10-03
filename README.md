# zig-agent-docs

Reference documents for AI coding agents working on Zig projects. Every
claim in them is checked against the real toolchain.

| File | What it is |
|---|---|
| [ZIG-0.17.md](ZIG-0.17.md) | Zig 0.17 for agents whose knowledge stops at 0.15: what changed in 0.16 and 0.17, the silent traps, a compile-error decoder, a migration playbook, and copy-ready patterns, all verified against the 0.17.0 compiler. |
| [codebase-revamp.md](codebase-revamp.md) | A Claude Code skill that leads a subagent-team revamp of a codebase: correct, secure, complete, fast, small and well documented, on a `revamp` branch. It works from the project's toolchain reference (such as `ZIG-0.17.md`) rather than the model's memory. |

## Using them

Point an agent at the Zig reference from a project's `AGENTS.md`:

```markdown
**Zig 0.17.** Read [ZIG-0.17.md](https://raw.githubusercontent.com/shreeve/zig-agent-docs/main/ZIG-0.17.md)
before writing Zig, and check a std API in its source (`zig env` prints `std_dir`).
```

Install the skill for Claude Code (user level, available in every project):

```bash
mkdir -p ~/.claude/skills/codebase-revamp
curl -fsSL https://raw.githubusercontent.com/shreeve/zig-agent-docs/main/codebase-revamp.md \
    -o ~/.claude/skills/codebase-revamp/SKILL.md
```

Then ask Claude Code to revamp a repository, or run `/codebase-revamp`.
Run it on a project after its Zig 0.17 port has landed, so the revamp starts
from 0.17 code.

## Mirror

The repository is mirrored to a gist (the same files, the same history):
https://gist.github.com/shreeve/57a74df35e17dacb30dcaa5d5164a27f. Files stay
at the top level, because a gist cannot hold directories.
