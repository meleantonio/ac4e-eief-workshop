# Version control rules

Linked from [`AGENTS.md`](../../AGENTS.md).

## Flow

1. **Issue first.** Non-trivial work starts from an issue card (`templates/issue_card.md`)
   with a "Done when" list.
2. **Branch.** Create a branch from an up-to-date `main`, named after the issue:
   `<issue-slug>` (for example `ck-data-cleaning`). Never commit to `main`.
3. **Commit.** Small commits, one logical change each. Message: short summary line
   in the imperative ("Add sample-restriction table"), then a line on why.
4. **Verify** with the check command (see [verification](verification.md)) before
   opening or updating a pull request.
5. **Pull request.** One issue per PR. The description says what changed, why, the
   verification output, and anything the reviewer must check by hand.
6. **Review and merge** are done by a human.

## The agent must ask before it

- pushes to the remote, opens or merges a PR;
- force-pushes, rebases, amends, resets or deletes a branch;
- commits files outside the scope of the current issue.

## Never commit

- raw or confidential data, `.env`, API keys, tokens;
- large generated files (logs, caches, `.venv/`) — check `.gitignore` first;
- edits to `examples/*/data/` or to tests made to force a pass.

## Before committing, check

```bash
git status
git diff --staged
```

Read the diff. If a file you did not mean to change is listed, unstage it.
