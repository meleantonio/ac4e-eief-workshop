# Tool lane: Cursor

Install steps are in [`SETUP.md`](../SETUP.md).

1. Install Cursor and sign in.
2. Open this project folder.
3. Use **Ask** to read without editing, **Plan** before a multi-file change, and
   **Agent** to do the work.
4. First instruction (in Ask): "Read `AGENTS.md`. What rules are active?"

## Where each concept lives

| Concept | In Cursor |
| --- | --- |
| Rules file | `AGENTS.md`, read automatically; optional extra rules in `.cursor/rules/` |
| To-do list | Plan mode; the agent shows a to-do list you can edit before it builds |
| Skills | Copy `agent-harness/cursor/skills/<name>/` to `.cursor/skills/<name>/`; call by name |
| Sub-agents | Copy `agent-harness/cursor/subagents/<name>.md` to `.cursor/agents/`; "Use `data-reviewer` on the panel" |
| Goal | No `/goal` command: make the goal the last line of your instructions |
| Cloud agents from issues | Cloud Agents; start one from the Cursor app or with `@cursor` in a GitHub issue |
| Automatic check after each edit (optional) | `.cursor/hooks.json`; example in `agent-harness/cursor/hooks/` |

## Habits

- Give each cloud agent its own separate copy (branch) and one issue card.
- The reviewer files set `readonly: true`. That is the bound for those jobs. A sub-agent can also write when the job asks for a file or a figure.
- Read the list of changes and run the check command before you merge.

Menu names change between versions. Check them in your installed version.
