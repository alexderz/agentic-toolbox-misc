# Graphistry / Louie.ai follow-up delta — 2026-10-29

Baseline: [2026-10-07-graphistry-investigation-harnesses.md](2026-10-07-graphistry-investigation-harnesses.md). Previous delta: [2026-10-28-graphistry-delta.md](2026-10-28-graphistry-delta.md). Checked Thu Oct 29 2026 ~9:55am CT.

## X, @Graphistry: LASCON 2026 talk on Moltbook (Oct 28 2026 ~7:44pm CT)

- Post: https://x.com/Graphistry/status/2115605714970230793 . "When humans aren't users but owners, what does a botnet even look like?" At LASCON 2026 in Austin, Graphistry visualization engineer Manfred Cheung will present findings from investigating Moltbook, a social network built for AI agents (post text continues past the API excerpt).
- Quote by @lmeyerov (Oct 29 2026 ~12:44am CT): https://x.com/lmeyerov/status/2115681186756559035 . Describes it as internal research by the @graphistry / @louie_ai team on agent activity: "when your users are agents to begin with, what does anti-bot detection work even mean?"

## GitHub, graphistry-skills PR #38 merged (Oct 28 2026 ~12:20pm CT)

- https://github.com/graphistry/graphistry-skills/pull/38 (from 2026-10-28 delta) merged as 7d9fe3e. No new release; latest tag still v0.5.2. Changes sit under CHANGELOG `[Development]`.
- Extra commit before merge, 69d4e3c (Oct 28 ~9:21am CT), "color id queries directly and name the items asked for": on servers whose `create_collection` takes a query returning node ids, color a top N / community / neighbors by passing that query instead of pasting an id list; ids in such queries returned as stored (no `toString()`); multi-row id queries are read-only; `query_graph` warnings on undirected / variable-length / multi-hop patterns are not an answer until checked one hop at a time; who/which/top-N answers name the items. Files: `.agents/skills/graphistry-mcp/SKILL.md` +44/−30, `CHANGELOG.md` +1, `evals/journeys/graphistry_mcp_cypher_eval_v1.json` +8/−8.
- License: repo license unchanged from baseline.

## Unchanged

- pygraphistry: latest release 0.61.2 (PyPI `graphistry` 0.61.2); no new merges since Oct 27.
- louie-py: PyPI `louieai` still 0.9.0; no new commits.
- bsides-augusta-2026: no commits since Oct 23.
- Graphistry blog: no new post confirmed.
