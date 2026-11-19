# dixon07marino-skills

Personal skill marketplace for Claude Code with one plugin, `dx`. Commands are `/dx:<skill>`.

`dx` is based on [pstack](https://github.com/cursor/plugins/tree/main/pstack) by Lauren Tan (MIT), pruned and extended with my own skills (`/dx:sdd`) and a trimmed set from [mattpocock/skills](https://github.com/mattpocock/skills) (MIT). See `NOTICES.md` for credits and local changes.

## Install

```
claude plugin marketplace add Dixon07Marino/dixon07marino-skills
claude plugin install dx@dixon07marino-skills
```

Then run `/reload-plugins` inside Claude Code.

## Layout

- `pstack/`: source of truth for the plugin (skills, agents, docs).
- `harness/pstack/claude-code/`: generated Claude Code tree that the marketplace installs. Do not edit by hand. After changing `pstack/`, run `node scripts/generate-pstack-harness-trees.mjs`.
- `scripts/`: validation (`validate-plugins.mjs`, `check-pstack-docs.mjs`) and the tree generator.
- `NOTICES.md`: third-party credits and the changes made to Matt Pocock's skills.

## Update

Edit `pstack/`, regenerate, bump `version` in `pstack/plugin.json`, commit and push. Then:

```
claude plugin marketplace update dixon07marino-skills
claude plugin update dx@dixon07marino-skills
```

## Syncing with upstream

`git fetch upstream && git merge upstream/main`. Upstream is `cursor/plugins`. Re-delete any directories git reports as modify/delete conflicts. Matt's skills are vendored, so pull his changes by hand from his repo.
