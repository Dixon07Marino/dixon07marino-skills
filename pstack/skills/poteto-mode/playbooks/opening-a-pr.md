### Opening a PR

Invoked at the end of every other playbook.

Work from a git worktree off trunk, and keep unrelated work out of it. Rebase into small, landable commits. Strip slop from the diff before commit: comments that restate code, dead code, and needless abstractions.

Title: `type(scope): subject`, naming a real symbol when one carries the change. Body: a one-minute briefing under 40 lines with these `##` headings in order, dropping empty ones: `## Why`, `## What changed`, `## Scope`, `## Tradeoffs` (only rejected alternatives a reviewer would otherwise ask about), `## Blast Radius`, `## Verification`.

Stack follow-ups by base branch. Open PRs ready, never as a draft: `gh pr create` without `--draft`, or `az repos pr create --draft false --source-branch <b> --target-branch <trunk> --title <t> --description <d>`. Opening a PR does not start a babysit.
