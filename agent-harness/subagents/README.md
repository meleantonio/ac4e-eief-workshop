# Sub-agents

A sub-agent is another agent you hand a piece of the work. It has its own
conversation and its own instructions. Inside the bounds you set, it can read,
write, check, and decide. It hands back whatever that job needs: a cleaned file,
a figure, a review, a pull request, or a short report. A summary is one possible
result, not the definition.

A Skill is a repeatable set of instructions followed in the same conversation.
A sub-agent is a separate agent with a fresh context that carries out a piece of
work on its own.

**Use a Skill** when the same steps should be reused in place. **Use a sub-agent**
when the piece of work needs its own focus, its own files, or would crowd the
main conversation (see [`../skills/README.md`](../skills/README.md)).

Think of a research assistant who redoes the Card–Krueger sample, rebuilds the
parallel-trends figure, or reviews the cleaning, and hands the result back.

## How to use one

1. Call it by name and hand it one piece of work: "Use `data-reviewer` on `examples/card-krueger-toy/`."
2. Set the bounds: what it may read, write, check, or decide.
3. It works in its own conversation.
4. Read what it hands back before you act.

The reviewers in this folder are bounded to read-only reviews. That bound is the
job, not the definition. A sub-agent can also write when the card asks for a
cleaned file or the parallel-trends figure.

## Where they live

- Claude Code: `.claude/agents/` (portable copy: `../claude/agents/`)
- Cursor: copy `../cursor/subagents/` into `.cursor/agents/`
- Codex: copy `../codex/agents/` into `.codex/agents/`

## Keeping the reviewers read-only

`data-reviewer`, `literature-reviewer` and `pr-reviewer` are bounded to a review.
Each tool does that differently:

- **Claude Code:** the files allow only reading tools (`Read`, `Grep`, `Glob`) and
  block editing and running commands.
- **Cursor:** the files set `readonly: true`, which blocks edits and commands.
- **Codex:** a sub-agent follows the permissions of the chat that calls it. Set the
  chat to read-only before you call a reviewer; see `../codex/README.md`.
