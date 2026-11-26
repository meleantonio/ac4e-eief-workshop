# Tool lane: Claude Code (app or command window)

The primary lane for the workshop. Install steps are in [`SETUP.md`](../SETUP.md).

1. Install Claude Code and sign in.
2. Open this project folder.
3. First instruction: "Read `AGENTS.md` and `CLAUDE.md`. Do not edit files. Summarise the rules."

## Where each concept lives

| Concept | In Claude Code |
| --- | --- |
| Rules file | `CLAUDE.md`, which points to `AGENTS.md` |
| To-do list | Plan mode (Shift+Tab); the agent shows its to-do list before acting |
| Skills | `.claude/skills/<name>/SKILL.md`; call by name, e.g. "Use the `replication-checker` Skill" |
| Sub-agents | `.claude/agents/<name>.md`; "Use the `data-reviewer` sub-agent on `examples/card-krueger-toy/`"; `/agents` lists them |
| Goal | `/goal <one sentence>`; `/goal clear` removes it |
| Cloud agents from issues | Claude Code on the web, or `@claude` in a GitHub issue if the Claude GitHub app is installed |
| Automatic check after each edit (optional) | `.claude/settings.json`; example in `agent-harness/claude/hooks/` |

## Habits

- Start read-only. Allow edits only once the goal and allowed files are clear.
- The reviewer sub-agents in this workshop are read-only. That is the bound for those jobs. A sub-agent can also write when the job asks for a file or a figure.
- Read a Skill before you run it.
- Read the list of changes and run the check command before you merge.

Menu names change between versions. Check them in your installed version.
