# Tool lane: Codex (app or command window)

Install steps are in [`SETUP.md`](../SETUP.md).

1. Install Codex and sign in.
2. Open this project folder.
3. First instruction: "Read `AGENTS.md`. Do not edit files. Summarise the rules and the check command."

## Where each concept lives

| Concept | In Codex |
| --- | --- |
| Rules file | `AGENTS.md`, read automatically |
| To-do list | Ask for a plan first ("Plan only, do not edit"); Codex shows its to-do list as it works |
| Skills | `.agents/skills/<name>/SKILL.md`; call by name |
| Sub-agents | Copy `agent-harness/codex/agents/*.toml` to `.codex/agents/`; "Use `data-reviewer` to review the panel" |
| Goal | `/goal <one sentence>` (Codex 0.128.0 or later); `/goal clear` removes it |
| Cloud agents from issues | Codex cloud tasks, or `@codex` in a GitHub issue if the Codex GitHub app is installed |
| Automatic check after each edit (optional) | `.codex/hooks.json`; example in `agent-harness/codex/hooks/` |

## Habits

- Set the chat to read-only before you call a reviewer: a Codex sub-agent follows
  the permissions of the chat that calls it (see `agent-harness/codex/README.md`).
  A review is one result. When the job is a cleaned file or a figure, allow the
  writes that job needs.
- Read the list of changes before accepting edits.
- Run the check command before you merge.

Menu names change between versions. Check them in your installed version.
