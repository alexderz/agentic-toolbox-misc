# Graphistry / Louie.ai follow-up delta — 2026-10-26

Baseline: [2026-10-07-graphistry-investigation-harnesses.md](2026-10-07-graphistry-investigation-harnesses.md). Previous delta: [2026-10-23-graphistry-delta.md](2026-10-23-graphistry-delta.md). Checked Mon Oct 26 2026 ~9:55am CT.

## pygraphistry 0.61.2 (released Oct 23 2026 ~8:27pm CT)

- Release: https://github.com/graphistry/pygraphistry/releases/tag/0.61.2 ; PyPI `graphistry` 0.61.2: https://pypi.org/project/graphistry/0.61.2/ . License BSD-3-Clause.
- Patch release for GFQL / Cypher correctness: Cypher queries on graphs without edges, cuDF UNION types, grouping by a property named `name`, pattern predicates with aggregates, whole-node `RETURN DISTINCT`, duplicate seed-ID multiplicity, temporal Cypher parameters (structured E302 errors for malformed bounds), plus igraph / GEXF / cuGraph attribute preservation.
- After the release, on main (Oct 25–26, unreleased): remote GFQL wire fixes (#2244, #2245), static conversion validation (#2250), old/current server wire contract tests (#2251).

## pygraphistry #2229: hybrid-agent planner/worker skills keep polling (merged Oct 25 2026 ~3:17pm CT)

- PR: https://github.com/graphistry/pygraphistry/pull/2229 , "docs(skills): keep live planner and worker goals polling", +7 −3, docs only.
- Files: `.agents/skills/hybrid-agent-planner/SKILL.md`, `.agents/skills/hybrid-agent-planner/references/coordination.md`, `.agents/skills/hybrid-agent-worker/SKILL.md`.
- Worker polls the planner mailbox and known gate every 2–3 minutes while waiting on live review, clearance, or CI, each wait at most 60 seconds; checks planner messages after long tool waits and before the next external side effect. Existing blocked-state exit kept.

## Other

- bsides-augusta-2026 (no license), Oct 23: student-feedback commit (Q4/Q6 marked as needing reach beyond Splunk in Lab 2, cross-model contamination comparison added to Lab 4, capstone reflection prompts). https://github.com/graphistry/bsides-augusta-2026
- X, @lmeyerov, Oct 26 ~9:00am CT: replies to @MalwareTechBlog / @ZackKorman describing Louie's use by SOC and IR teams (gov, MSSPs) for ticket queues and live incidents, and lower LLM cost enabling a move from alerts to events. https://x.com/lmeyerov/status/2114718891746488670 , https://x.com/lmeyerov/status/2114719392558886953

## Unchanged

- louie-py: no new commits on main; PyPI `louieai` still 0.9.0.
- graphistry-skills: no change since #36 (latest release v0.5.2); graphistry-mcp unchanged.
- Graphistry blog: no new post confirmed (blog/RSS behind a bot check).
