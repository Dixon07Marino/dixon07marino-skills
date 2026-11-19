# Third-party notices

## Matt Pocock skills (MIT)

Vendored from https://github.com/mattpocock/skills (MIT), commit 5863806.
Only skills/engineering and skills/productivity are included, as listed in the upstream plugin manifest.
Upstream is also forked at https://github.com/Dixon07Marino/skills.

## Local changes (2026-11-18)
Removed skills: grill-with-docs, research, ask-matt, implement, implement-spec, triage, setup-matt-pocock-skills, to-spec, to-tickets, wayfinder, writing-for-agents, handoff, wait-what. The plugin manifest lists the 14 that remain.
Removed the two upstream README.md index files (they listed removed skills).
Edited: code-review (spec comes from sdd/<topic>/spec.md, no tracker), retro (no writing-for-agents call).
The ticket flow (to-spec, to-tickets) was folded into pstack/skills/sdd instead of being installed.
2026-11-18 (2): code-review is now manual only (disable-model-invocation) so Claude Code's built-in /code-review takes priority; run it as /mattpocock-skills:code-review. diagnosing-bugs caps flaky-bug looping at 10 repetitions, 2 workers, nice -n 19 (project limits win).

### License

MIT License

Copyright (c) 2026 Matt Pocock

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
