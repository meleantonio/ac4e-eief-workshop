# CLAUDE.md

All project rules are in `AGENTS.md`, imported here so Claude Code loads them:

@AGENTS.md

## In brief

- **Project:** synthetic Card–Krueger minimum-wage panel (NJ vs PA, 1992) used as the
  teaching example for *Agentic Coding for Economists*. No research claims.
- **Folder map:** see `AGENTS.md`. Research code is in `examples/card-krueger-toy/`.
- **Version control:** branch from `main`, one issue per branch, human merges.
  Ask before pushing. See `docs/agent-rules/version_control.md`.
- **Verification:** run the pytest check command and quote its output before saying
  a task is done. See `docs/agent-rules/verification.md`.

## Claude Code specifics

| Piece | Path |
| --- | --- |
| Skills | `.claude/skills/*/SKILL.md` (e.g. `replication-checker`, `sample-restrictions-note`) |
| Sub-agents | `.claude/agents/*.md` (`data-reviewer`, `literature-reviewer`, `pr-reviewer`, `loop-verifier`) |
| Hooks | `.claude/hooks/` + `.claude/settings.example.json` (optional) |
| MCP | `agent-harness/claude/mcp/mcp.json.example` → `.mcp.json` (optional) |

- Prefer read-only prompts until the issue's acceptance criteria are clear.
- Confidential data: refuse and point to `docs/privacy_boundary.md`.
