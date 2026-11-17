# plugins (personal pstack fork)

Personal fork of [cursor/plugins](https://github.com/cursor/plugins), pruned to [pstack](pstack/) by Lauren Tan (MIT). Everything else from upstream was removed.

- `pstack/`: source of truth for skills, agents, and docs (Cursor reads this directly).
- `harness/pstack/claude-code/`: generated Claude Code tree. Do not edit by hand; run `node scripts/generate-pstack-harness-trees.mjs` after changing `pstack/`.
- `scripts/validate-plugins.mjs`: validates manifests.

## Install in Claude Code

```
/plugin marketplace add Dixon07Marino/plugins
/plugin install pstack@cursor-plugins
```

## Syncing with upstream

`git fetch upstream && git merge upstream/main`. Re-delete any non-pstack directories that git reports as modify/delete conflicts.
