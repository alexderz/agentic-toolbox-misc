# Graphistry / Louie.ai follow-up delta — 2026-10-28

Baseline: [2026-10-07-graphistry-investigation-harnesses.md](2026-10-07-graphistry-investigation-harnesses.md). Previous delta: [2026-10-27-graphistry-delta.md](2026-10-27-graphistry-delta.md). Checked Wed Oct 28 2026 ~9:50am CT.

## X, @lmeyerov: Unprompted talk highlights and slides (Oct 28 2026 ~9:08–9:22am CT)

- Post: https://x.com/lmeyerov/status/2115445602142314885 . Highlights from the Oct 27 @unpromptedconf talk on what evals show is changing in AI SOC and AI investigations, and on making reliability an engineering discipline. First highlight: "Western open weights models are back", naming @reflection_ai BEAM 1.0 and @MistralAI Large 4 (post includes an image).
- Slides: https://x.com/lmeyerov/status/2115448324715397194 , linking https://docs.google.com/presentation/d/1parzLZCLdQwq9WcMkWTeFpE5TZXEhmF2xbxEze_ZmiY
- Reply: https://x.com/lmeyerov/status/2115449038220960024 . States one timeline-generation task can take 250 tool calls, and the full set of ~59 tasks represents 20+ hours of professional analyst time.

## GitHub, graphistry-skills PR #38 (open, opened Oct 27 2026 ~4:20pm CT)

- https://github.com/graphistry/graphistry-skills/pull/38 , "fix(graphistry-mcp): rules from a live Cypher eval", closes #37. Author dess890. +321/−39 across `.agents/skills/graphistry-mcp/SKILL.md`, `CHANGELOG.md`, and new `evals/journeys/graphistry_mcp_cypher_eval_v1.json` (8 cases).
- Adds Cypher-only MCP skill rules: compare ids as text (`toString`), `toFloat()` for numbers stored as text, keep ties at a top-N cutoff, lowercase both sides of free-text `CONTAINS`, filter on every named node kind, new recipes (largest communities, community of a node, id list grouped by degree). SKILL.md 245 to 285 lines.
- Reported evals (Claude as MCP client, main vs branch): new journey Haiku 11/16 to 14/16; 32-case oracle suite Haiku 52/64 to 54/64, Opus 59/64 to 60/64.
- Companion changes referenced: server-side graphistry/graphistry#3600 and Louie talk2graph skill port in graphistry/graphistrygpt#4369 (both private, not checked).
- License: repo license unchanged from baseline.

## Unchanged

- pygraphistry: no new release (latest 0.61.2); merged #2183 (CI Cypher parity dedupe) Oct 27 ~4:03pm CT, not agent-related.
- louie-py: PyPI `louieai` still 0.9.0; no new commits.
- graphistry-skills: latest release still v0.5.2.
- bsides-augusta-2026: no commits since Oct 23.
- Graphistry blog: no new post confirmed.
