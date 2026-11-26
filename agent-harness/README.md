# Agent set-up: Skills, sub-agents and checks

This folder holds the workshop set-up for **Claude Code**, **Codex** and **Cursor**:
the same Skills and sub-agents, saved in each tool's own format. The set-up is the
rules file (`AGENTS.md`) plus Skills, sub-agents and checks.

## Skill or sub-agent?

- **Skill** = a repeatable set of instructions followed in the same conversation.
  Use one when the same steps should be reused in place. Example: "Recompute the
  DiD the same way each time."
- **Sub-agent** = another agent you hand a piece of the work. It has its own
  conversation and its own instructions. Inside the bounds you set, it can read,
  write, check, and decide. It hands back whatever that job needs: a cleaned file,
  a figure, a review, a pull request, or a short report. A summary is one possible
  result, not the definition. Use one when the piece of work needs its own focus,
  its own files, or would crowd the main conversation. Example: redo the
  Card–Krueger sample, rebuild the parallel-trends figure, or review the cleaning,
  and hand back the result.

A Skill stays in this conversation. A sub-agent is a separate agent with a fresh
context that carries out a piece of work on its own. You set the bounds and you
read what it hands back.

## Skills on the workshop path

| Skill | Use when | Concept |
| --- | --- | --- |
| `replication-checker` | Checking whether the example reproduces its numbers from a fresh start | Skills, verification |
| `sample-restrictions-note` | Listing every rule that drops stores, with the count after each | Create a Skill (worked example) |
| `hooks` | Setting up the optional automatic check after each edit | Verification (optional) |
| `loop-on-verification` | Letting the agent check its own work before you review | Verification (optional) |

Off the path: `literature-mapper` (optional mention only) and `sdd`.

## Sub-agents on the workshop path

These four are bounded to a review. That bound is the job, not the definition of
a sub-agent. A sub-agent can also write when the job asks for a cleaned file or
the parallel-trends figure.

| Sub-agent | What this one hands back | Concept |
| --- | --- | --- |
| `data-reviewer` | A review of panel balance, missing values, and NJ/PA coding | Sub-agents, verification |
| `literature-reviewer` | A review of references and literature claims | Using sub-agents |
| `pr-reviewer` | A review of a returned pull request against its card | Issue-board swarm |
| `loop-verifier` | A pass/fail check and the next action (optional) | Verification |

Off the path: `sdd-orchestrator`.

## Where each tool keeps them

| Tool | Skills | Sub-agents | Copies in this folder |
| --- | --- | --- | --- |
| **Claude Code** | `.claude/skills/<name>/SKILL.md` | `.claude/agents/<name>.md` | `claude/` |
| **Codex** | `.agents/skills/<name>/SKILL.md` | `.codex/agents/<name>.toml` | `codex/` |
| **Cursor** | `.cursor/skills/<name>/SKILL.md` | `.cursor/agents/<name>.md` | `cursor/` |

The project folder already has working copies in `.claude/` and `.agents/skills/`.
For Cursor or Codex sub-agents, copy the files from `cursor/` or `codex/` after
reading them. Skill copies must stay identical in every location.

Each tool folder also holds an optional automatic check after each edit (`hooks/`)
and an optional data connection example (`mcp/`, prework only).

## Other files

- [`autonomous_agent_risk_card.md`](autonomous_agent_risk_card.md): fill in before
  any cloud agent works on the project.
- [`mcp/fred/`](mcp/fred/): optional FRED data connection, not used in the room.

Menu names change between versions. Check them in your installed tool.
