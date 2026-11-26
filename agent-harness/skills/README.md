# Skills

A Skill is a repeatable set of instructions followed in the same conversation.
The agent follows it the same way every time, and you can share it with coauthors.

**Use a Skill** when the same steps should be reused in place. When the piece of
work needs its own focus, its own files, or would crowd the main conversation,
use a sub-agent (see [`../subagents/README.md`](../subagents/README.md)).

The Skills live in one folder per tool, with identical files:

- Claude Code: `.claude/skills/` (portable copy: `../claude/skills/`)
- Codex: `.agents/skills/` (portable copy: `../codex/skills/`)
- Cursor: copy `../cursor/skills/` into `.cursor/skills/` after reading it

Start with `replication-checker` and `sample-restrictions-note`. To write
your own, use [`../../templates/skill_template.md`](../../templates/skill_template.md).
Read a Skill before you run it.
