# AGENTS.md

Rules for any coding agent (Claude Code, Codex, Cursor) working in this repository.
Keep this file short. Detailed procedures live in `docs/agent-rules/` and are linked below.

## Project

Participant repository for *Agentic Coding for Economists* (EIEF / Luiss, 26–27 Nov 2026).
The running research example is a **synthetic** Card–Krueger (1994) minimum-wage panel:
fast-food employment (FTE) in New Jersey (treatment) vs eastern Pennsylvania (comparison),
before and after NJ's April 1992 minimum-wage increase, compared with an unweighted 2x2
difference-in-differences.

The data are hand-written teaching data. They support **no research or causal claim**.

## Folder map

| Path | What it holds |
| --- | --- |
| `examples/card-krueger-toy/` | The research example: `data/` (never edit), `src/` (analysis), `tests/`, `faults/` (planted errors) |
| `examples/card-krueger-swarm/`, `examples/card-krueger-goals/` | Issue cards and goal statements for the example |
| `examples/mini-economics/` | Second test suite used by the check command |
| `exercises/`, `sessions/`, `demos/` | Workshop exercises, slot outlines, demo prompts |
| `notes/` | Participant answers (the agent writes here only when asked) |
| `templates/` | Forms to copy: issue card, task contract, provenance manifest, etc. |
| `docs/` | Prework, privacy boundary, project brief; `docs/agent-rules/` for agent procedures |
| `.claude/` | Claude Code skills, sub-agents and hooks |
| `agent-harness/` | Portable copies for other agents; autonomous-agent risk card |
| `replication/` | Packaging and replication instructions |

## Core rules

1. **Never edit raw data.** Files in `examples/*/data/` and any `data/raw/` folder are read-only.
2. **Never edit tests to make them pass.** Fix the code or report the failure.
3. **Do not certify identification, causality or interpretation.** Report numbers; a human interprets them.
4. **Keep the synthetic-data caveat** in every output that shows estimates. No significance stars.
5. **No confidential data, secrets or `.env` files** in prompts, commits or cloud agents.
6. **Plan before editing more than one file**, and keep edits scoped to the current task.
7. **Use relative paths** and document sources, units, transformations and sample restrictions.

Details: [data and privacy](docs/agent-rules/data_and_privacy.md).

## Version control

- Work on a branch, never directly on `main`: issue → branch → pull request.
- One issue per branch; small commits with messages that say what and why.
- Do not push, merge, force-push or rewrite history unless the human asks.

Details: [version control](docs/agent-rules/version_control.md).

## Verification

Run before saying any task is done, and quote the result:

```bash
python3 -m pytest examples/card-krueger-toy/tests examples/mini-economics/tests
```

On Windows use `python` instead of `python3`. Never report "green" without having run it.
A passing check shows only that the code reproduces the teaching numbers.

Details: [verification](docs/agent-rules/verification.md).
