# Graphistry / Louie.ai follow-up delta — 2026-11-02

Baseline: [2026-10-07-graphistry-investigation-harnesses.md](2026-10-07-graphistry-investigation-harnesses.md). Previous delta: [2026-10-29-graphistry-delta.md](2026-10-29-graphistry-delta.md). Checked Mon Nov 2 2026 ~9:50am CT, covering Oct 30 ~10am CT onward.

## X, @lmeyerov on Louie read-only investigations (Oct 30 2026 ~7:19pm CT)

- Post: https://x.com/lmeyerov/status/2116339171975745777 (reply to @kaseyklimes). Excerpt: "super easy to go aggressive with @louie_ai when they run read-only investigations, and easy for us to make that better every month. super valuable even if teams stop here. once they want actions like \"disconnect device from the internet\", game changes, and if they…" (text continues past the API excerpt).

## GitHub, pygraphistry PR #2265 merged (Oct 31 2026 ~2:50pm CT)

- https://github.com/graphistry/pygraphistry/pull/2265 , "docs(skills): avoid blocked subagent filenames", author lmeyerov, merge commit 64485b3.
- Adds a rule to the repo's agent skills that Markdown artifacts written by subagents must not have basenames starting with `report`, `summary`, `findings`, or `analysis`, citing Claude Code refusing such subagent Writes (anthropics/claude-code#44657). Renames prescribed review and test-amplification artifacts.
- Files: `.agents/skills/{hybrid-agent-planner,hybrid-agent-worker,plan}/SKILL.md` +1 each, `.agents/skills/review/SKILL.md` +5/−3, `.agents/skills/test-amplification/SKILL.md` +3/−1, `tests/test_skill_filenames.py` +56.
- License: pygraphistry repo license unchanged (BSD-3-Clause). No release; latest tag still 0.61.2.

## Unchanged

- Graphistry blog: newest post still Oct 9 2026 (GFQL indexes).
- pygraphistry: other merges since Oct 30 are GFQL/Cypher/cuDF fixes (#2261–#2274); PyPI `graphistry` 0.61.2.
- graphistry-skills: latest tag v0.5.2, no commits since PR #38.
- louie-py: PyPI `louieai` 0.9.0, no new commits.
- graphistry-mcp, louie.ai-docs, bsides-augusta-2026: no new commits. No new graphistry org repos.
- @Graphistry: no posts since Oct 28.
