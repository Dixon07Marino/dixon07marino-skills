# dixon07marino-skills

Personal skill marketplace for Claude Code. Two plugins:

| Plugin | Commands | What it is |
|---|---|---|
| `dx` | `/dx:<skill>` | My skill set, based on [pstack](https://github.com/cursor/plugins/tree/main/pstack) by Lauren Tan (MIT), pruned and extended. Includes `/dx:sdd`. |
| `mattpocock-skills` | `/mattpocock-skills:<skill>` | A trimmed copy of [mattpocock/skills](https://github.com/mattpocock/skills) (MIT). See `mattpocock/UPSTREAM.md`. |

## Install

```
claude plugin marketplace add Dixon07Marino/dixon07marino-skills
claude plugin install dx@dixon07marino-skills
claude plugin install mattpocock-skills@dixon07marino-skills
```

Then run `/reload-plugins` inside Claude Code. Install both plugins: `dx:sdd` calls `tdd`, `grilling` and `code-review` from the Matt plugin.

## Layout

- `pstack/`: source of truth for the `dx` plugin (skills, agents, docs).
- `harness/pstack/claude-code/`: generated Claude Code tree that the marketplace installs. Do not edit by hand. After changing `pstack/`, run `node scripts/generate-pstack-harness-trees.mjs`.
- `mattpocock/`: the second plugin.
- `scripts/`: validation (`validate-plugins.mjs`, `check-pstack-docs.mjs`) and the tree generator.

## Syncing with upstream

`git fetch upstream && git merge upstream/main`. Upstream is `cursor/plugins`. Re-delete any directories git reports as modify/delete conflicts.
