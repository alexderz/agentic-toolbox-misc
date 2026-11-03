# Graphistry / Louie.ai follow-up delta — 2026-10-22

Baseline: [2026-10-07-graphistry-investigation-harnesses.md](2026-10-07-graphistry-investigation-harnesses.md). Previous delta: [2026-10-21-graphistry-delta.md](2026-10-21-graphistry-delta.md). Checked Thu Oct 22 2026 ~9:50am CT.

## New: `investigation-loop` skill in the BSides Augusta 2026 repo

- File: https://github.com/graphistry/bsides-augusta-2026/blob/main/resources/skills/investigation-loop/SKILL.md (added 2026-10-22 ~7:52am CT, ~3.9 KB). Repo has no LICENSE file.
- Description: "Multi-round alert investigation with analyst review between rounds."
- Round 1: restate the alert (entities, time), scope a time window (default one hour either side unless an alert-type skill or SOP says otherwise), plan three to six checks most decisive first, run them bounded by time window and row limit, report. Stop past about ten tool calls and move remaining checks to Next steps.
- Follow-up rounds take analyst replies `Run next steps N1, N3`, `Continue`, a free-form instruction, or a correction (re-examine, retract or revise). Each follow-up report starts with "What changed"; fixed per-round report format.
- Same day, same folder: `resources/PLAN.md` task plan template taken from pygraphistry ("Planning II"). Laya notebooks got a Colab setup cell (Labs 1 and 4).

## New (open PR): graphistry-skills #36, Cypher-first `graphistry-mcp` skill

- PR: https://github.com/graphistry/graphistry-skills/pull/36 (opened 2026-10-20 by dess890, last updated 2026-10-21; open, not merged; +324 −204). Repo license BSD-3-Clause.
- Makes Cypher the default way an MCP agent queries a live Graphistry graph: Graphistry runs a subset of openCypher transpiled into GFQL. Server errors (`invalid-cypher-syntax`, `unsupported-cypher-query`, `column-not-found`) drive the fix-and-retry loop. GFQL JSON forms move to `references/gfql-wire-format.md`; `SKILL.md` shrinks from 15.2k to 12.7k characters.
- Server dependency per PR: graphistry#3600 (pygraphistry 0.60). Companion: graphistrygpt#4318 (Louie's talk2graph skill).
- PR's eval (32 questions × 2 runs = 64 per setup, strict grading): Talk2Graph (Louie, gpt-5.6-sol medium) 60/64 current skill vs 62/64 Cypher-first; Claude Haiku direct to MCP 55/64 vs 63/64. Haiku mean latency 21s vs 17s.

## Unchanged

- Graphistry blog/RSS still returns a captcha redirect; no new post confirmed.
- Louie.ai /blog still 404.
- X: no @Graphistry or @LOUIE_AI posts since Oct 15; @lmeyerov Oct 21 posts off-topic (install cooldowns after LiteLLM PyPI compromise, startup equity).
- louie-py tip 2026-10-19 (no new release since v0.9.0, Jul 26). graphistry-mcp unchanged. louie.ai-docs PR #12 (Docker Compose tarball install guide) open, off-topic.
