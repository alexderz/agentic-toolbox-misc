# Graphistry / Louie.ai follow-up delta — 2026-10-23

Baseline: [2026-10-07-graphistry-investigation-harnesses.md](2026-10-07-graphistry-investigation-harnesses.md). Previous delta: [2026-10-22-graphistry-delta.md](2026-10-22-graphistry-delta.md). Checked Fri Oct 23 2026 ~9:50am CT.

## Merged: graphistry-skills #36, `graphistry-mcp` skill is now Cypher only

- PR: https://github.com/graphistry/graphistry-skills/pull/36, merged 2026-10-22 ~4:40pm CT (merge commit 586460b). Final title "feat(graphistry-mcp): make the skill Cypher only". Final size +445 −435 across 9 files. Repo license BSD-3-Clause.
- Cypher (a subset of openCypher transpiled into GFQL) is the only query language the skill teaches an MCP agent. The JSON GFQL reference `references/gfql-wire-format.md` is removed. New `references/connection.md` and `references/ip-classification.md`. `SKILL.md` is 15.5k characters.
- Coloring: one node alias, one directed hop of edges, or an `IN` id list; larger selections collected with `collect()` within the 64 KB query limit and 10 collections per session.
- Server needs, per PR: graphistry#3600 and graphistry#3617 (pygraphistry 0.61, Cypher node and edge collections). Companion: graphistrygpt#4369 (Louie talk2graph skill).
- Oct 22 Cypher-only evals from the PR: Claude Haiku to MCP targeted 20/20 (median 12s); Talk2Graph (Louie, gpt-5.6-sol medium) targeted 18/19 (median 30s); Talk2Graph lite 12/12 (median 42s). Each reported 0% confidently wrong answers.

## Related releases and commits

- pygraphistry 0.61.0 (2026-10-18) and 0.61.1 (2026-10-21): https://github.com/graphistry/pygraphistry/releases (BSD-3-Clause; PyPI `graphistry` 0.61.1).
- louie-py (Apache-2.0) main, Oct 22: "surface server error detail on streamed calls; current agent names in docs" (#54) and "org slug header follows the Graphistry server's slug rules" (#55). No new release; PyPI `louieai` still 0.9.0 (Jul 26).
- bsides-augusta-2026 (no license), Oct 22–23: Louie agent renames (SplunkAgent to Splunk, SplunkPassthroughAgent to SplunkPassthrough), `louieai>=0.7` uses `graphistry_server=`, Lab 3 Colab setup cell, README Day 2 schedule update, revised download instructions. https://github.com/graphistry/bsides-augusta-2026

## Unchanged

- Graphistry blog RSS still returns a captcha redirect; no new post confirmed.
- X: no @Graphistry, @LOUIE_AI, or @lmeyerov posts since Oct 22.
- graphistry-mcp unchanged (latest tag v0.1.4).
