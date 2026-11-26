# Official install and docs links

Links below were checked for the EIEF / Luiss pack in September 2026 (with Codex links re-checked 24 Nov 2026), though vendor pages move over time. When a setup step depends on your installed version, check these official pages and confirm the command on your machine. Step-by-step participant install instructions live in [`SETUP.md`](../SETUP.md).

## Git and GitHub

- Git downloads: <https://git-scm.com/downloads>
- GitHub signup: <https://github.com/signup>
- Course repository (the project folder and its change history): <https://github.com/meleantonio/ac4e-eief-workshop>

## Visual Studio Code

- Download: <https://code.visualstudio.com/download>
- macOS install: <https://code.visualstudio.com/docs/setup/mac>
- Windows install: <https://code.visualstudio.com/docs/setup/windows>
- Linux install: <https://code.visualstudio.com/docs/setup/linux>
- Claude Code extension (publisher Anthropic, id `anthropic.claude-code`): <https://marketplace.visualstudio.com/items?itemName=anthropic.claude-code>
- Claude Code in VS Code: <https://code.claude.com/docs/en/vscode>
- Codex extension (publisher OpenAI, id `openai.chatgpt`): <https://marketplace.visualstudio.com/items?itemName=openai.chatgpt>
- Codex in an editor: <https://learn.chatgpt.com/docs/codex/ide>

## Python

- Python downloads: <https://www.python.org/downloads/>
- `venv` docs: <https://docs.python.org/3/library/venv.html>
- pytest: <https://docs.pytest.org/>

## Claude Code (workshop primary)

- Overview and install: <https://code.claude.com/docs/en/overview>
- Settings: <https://code.claude.com/docs/en/settings>
- Skills (written procedures): <https://code.claude.com/docs/en/skills>
- Subagents (another agent for a piece of the work, with its own conversation): <https://code.claude.com/docs/en/sub-agents>
- Hooks: <https://code.claude.com/docs/en/hooks>
- Extra tools (MCP, an extra data tool such as FRED): <https://code.claude.com/docs/en/mcp>
- Native installer (macOS / Linux / WSL): `curl -fsSL https://claude.ai/install.sh | bash`
- Native installer (Windows PowerShell): `irm https://claude.ai/install.ps1 | iex`

## Codex

Checked 24 Nov 2026. `developers.openai.com/codex/...` redirects to these pages.

- Docs: <https://learn.chatgpt.com/docs>
- Command line: <https://learn.chatgpt.com/docs/codex/cli>
- App: <https://learn.chatgpt.com/docs/app>
- Cloud: <https://learn.chatgpt.com/docs/cloud>
- AGENTS.md guide: <https://learn.chatgpt.com/docs/agent-configuration/agents-md>
- Extra tools (MCP): <https://learn.chatgpt.com/docs/extend/mcp>
- Pricing and where each plan runs: <https://learn.chatgpt.com/docs/pricing>
- Using Codex with a ChatGPT plan: <https://help.openai.com/en/articles/11369540-using-codex-with-your-chatgpt-plan>
- Native installer (macOS / Linux): `curl -fsSL https://chatgpt.com/codex/install.sh | sh`

## Cursor

- Docs: <https://cursor.com/docs>
- Download: <https://cursor.com/download>
- Command line: <https://cursor.com/docs/cli/overview>
- Rules and AGENTS.md: <https://cursor.com/docs/rules>
- Skills: <https://cursor.com/docs/skills>
- Subagents: <https://cursor.com/docs/subagents>
- Extra tools (MCP): <https://cursor.com/docs/mcp>
- Cloud agents: <https://cursor.com/docs/cloud-agent>

## Extra data tool (FRED)

- FRED API keys: <https://fred.stlouisfed.org/docs/api/api_key.html>
- Workshop server: [`agent-harness/mcp/fred/README.md`](../agent-harness/mcp/fred/README.md)
- Your attempt note: [`docs/mcp_setup.md`](mcp_setup.md)

## Unsupervised systems (risk card only in-session)

- OpenClaw: <https://github.com/openclaw/openclaw>
- Hermes Agent: <https://hermes-agent.nousresearch.com/>
- Eve: <https://vercel.com/eve>

Do not connect those systems unsupervised to research data. Fill
[`agent-harness/autonomous_agent_risk_card.md`](../agent-harness/autonomous_agent_risk_card.md)
first.
