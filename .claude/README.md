# Claude Code examples for AC4E EIEF / Luiss

Project-scoped Claude Code configuration for this workshop. Cursor examples live in `agent-harness/cursor/` and are not preinstalled under `.cursor/`.

Verify paths and hook event names in your installed Claude Code version before a live demo.

## Layout

| Asset | Path | Notes |
| --- | --- | --- |
| Subagents | `.claude/agents/<name>.md` | YAML frontmatter + role prompt |
| Skills | `.claude/skills/<name>/SKILL.md` | Auto-discovered from repo root upward |
| Hooks | `.claude/settings.json` | Project hooks; see `settings.example.json` |
| Hook scripts | `.claude/hooks/*.py` | Called from settings |
| MCP | `.mcp.json` at repo root | See `agent-harness/claude/mcp/mcp.json.example` |

## Skills

Included skills:

- `sdd` — Spec-Driven Development lifecycle
- `replication-checker`, `literature-mapper`, `hooks`, `loop-on-verification`

Use `/skills` to browse. Invoke with `/skill-name` or let Claude match on description.

Official docs: [Claude Code skills](https://code.claude.com/docs/en/skills).

## Subagents

A sub-agent is another agent you hand a piece of the work. It has its own conversation and its own instructions. Inside the bounds you set, it can read, write, check, and decide. It hands back whatever that job needs: a cleaned file, a figure, a review, a pull request, or a short report. A summary is one possible result, not the definition. A Skill is a repeatable set of instructions followed in the same conversation.

The reviewers below are bounded to a review. Think of a research assistant who redoes the Card–Krueger sample, rebuilds the parallel-trends figure, or reviews the cleaning, and hands the result back.

Example prompt:

```text
Use the data-reviewer subagent to review examples/card-krueger-toy/ read-only.
```

Agents in `.claude/agents/`:

- `data-reviewer`, `literature-reviewer`, `sdd-orchestrator`
- `pr-reviewer`, `loop-verifier` (from agent harness)

Reviewer agents set `tools: Read, Grep, Glob` and disallow Write, Edit, NotebookEdit, Bash, and PowerShell. Claude Code ignores an unrecognized `readonly` field, so that field is not used here.

Official docs: [Claude Code subagents](https://code.claude.com/docs/en/sub-agents).

## Hooks

1. Copy `.claude/settings.example.json` to `.claude/settings.json` only when you intend to enable the hooks.
2. In an interactive session, accept the workspace trust dialog for this folder. That is what allows settings-file hooks to run. `/hooks` opens a read-only list of the hooks Claude Code loaded, with source and command. It does not approve them.
3. The example Stop hook appends a line to `notes/orchestration_log.md`.
4. Edit `examples/card-krueger-toy/src/did_analysis.py` and confirm pytest runs.

Official docs: [Claude Code hooks](https://code.claude.com/docs/en/hooks).

## Verification loops

Load `loop-on-verification` skill and invoke `loop-verifier` agent for one
execute-evaluate-revise iteration. Record verdicts in `notes/orchestration_log.md`.

## Portable harness

Tool-neutral teaching copies live in `agent-harness/claude/`.
