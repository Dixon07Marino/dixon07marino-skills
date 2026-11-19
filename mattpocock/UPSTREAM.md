Vendored from https://github.com/mattpocock/skills (MIT), commit 5863806.
Only skills/engineering and skills/productivity are included, as listed in the upstream plugin manifest.
Upstream is also forked at https://github.com/Dixon07Marino/skills.

## Local changes (2026-11-18)
Removed skills: grill-with-docs, research, ask-matt, implement, implement-spec, triage, setup-matt-pocock-skills, to-spec, to-tickets, wayfinder, writing-for-agents, handoff, wait-what. The plugin manifest lists the 14 that remain.
Removed the two upstream README.md index files (they listed removed skills).
Edited: code-review (spec comes from sdd/<topic>/spec.md, no tracker), retro (no writing-for-agents call).
The ticket flow (to-spec, to-tickets) was folded into pstack/skills/sdd instead of being installed.
2026-11-18 (2): code-review is now manual only (disable-model-invocation) so Claude Code's built-in /code-review takes priority; run it as /mattpocock-skills:code-review. diagnosing-bugs caps flaky-bug looping at 10 repetitions, 2 workers, nice -n 19 (project limits win).
