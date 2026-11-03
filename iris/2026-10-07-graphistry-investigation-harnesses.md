# GPT-6 Astra and Claude Fable 5.1 push the investigation frontier, but coding agents still trail investigation harnesses

Source: https://www.graphistry.com/blog/ai-coding-agents-investigation-harnesses
Author: graphistry staff
Published: October 7, 2026 (byline has a date and "2 min read"; no clock time)
Added Oct 7 2026 at Alex's request.

## Summary

Graphistry uses "investigation harness" for Louie.ai, their agent aimed at incident-response and analytics work, as distinct from a coding agent such as OpenAI Codex, Anthropic Claude Code, or the open-source OpenCode. On CyBT-CTF — 59 incident-response cases worked in Splunk — they report that newer frontier models in coding agents still lose to Louie with an older, smaller model: GPT-6 Astra reaches 69%, Claude Fable 5.1 reaches 61%, and Louie.ai with GPT-5.6 Sol reaches 76%. The same Sol model drops to 58% under Codex, and they say Louie on an older Opus 4.8 beats Claude Code on Fable 5.1. The pitch is that the harness moves investigation scores as much as the model does, and that Louie.ai is the harness they want used for this work.

They have not run Astra or Fable 5.1 inside Louie yet, and they say they expect that combination to score higher. On cost, Fable 5.1 is about $1.19 per solved case and Astra about $2.34; they say Astra is faster. Smaller models they name, GPT-5.6 Luna and GLM 5.3 Flash, solve over half the cases for under 10 cents each. The score and cost sections on the page are charts, not extra tables; the figures above are the ones written in the text. Deeper cards are on botsbench.com, which Graphistry runs.

## Key points

- CyBT-CTF is 59 incident-response cases in Splunk. This post's cards: https://botsbench.com/astra-cybt.html. Leaderboard: https://botsbench.com/. Method: https://botsbench.com/methodology.html.
- GPT-6 Astra is the strongest coding agent they have measured, at 69%. Claude Fable 5.1 is at 61%. Louie.ai with previous-generation GPT-5.6 Sol is at 76%.
- The same GPT-5.6 Sol falls to 58% in Codex. Louie on Opus 4.8 outperforms Claude Code on Fable 5.1. No separate percentage is given for that pair.
- Astra in Codex leads the coding agents only at high thinking effort. At low effort it falls to 53%. Cost is $2.34 per solved case, about twice Fable 5.1.
- Fable 5.1 scores the same at high and low effort, costs $1.19 per solved case, and refuses 2 of 59 cases, down from 5 for Fable 5.
- Astra scored about the same in open-source OpenCode as in Codex. The gap was larger between Claude Code / Fable 5.1 and OpenCode / Fable 5.1. They say coding agent vs investigation agent matters more than which vendor's coding agent you pick.
- Astra and Fable 5.1 have not been run in Louie yet. The post says those Louie numbers are still to be published.
- Fable 5.1 is cheaper per solved case; Astra is faster. GPT-5.6 Luna and GLM 5.3 Flash solve over half the cases for under 10 cents each. They say frontier-model cost is hard to justify without a better harness.
- Events named: BSides NYC, BSides Augusta (including their training, or a later online training), [Un]Prompted SF, and LASCON in Austin. The online training link in the post is https://louie.ai/trainings.

## Access

Checked Oct 7 2026. URLs below returned a page.

- Louie.ai public entry (Early Access on the page; no separate login URL was on it): https://louie.ai/
- Louie trainings, linked from the post: https://louie.ai/trainings
- Graphistry Hub signup: https://hub.graphistry.com/accounts/signup
- Graphistry Hub login: https://hub.graphistry.com/accounts/login
- Deployment overview: https://www.graphistry.com/get-started
- Graphistry REST API docs: https://hub.graphistry.com/docs/api/
- PyGraphistry docs: https://pygraphistry.readthedocs.io/en/latest/
- PyGraphistry repo: https://github.com/graphistry/pygraphistry
- Louie Python client: https://github.com/graphistry/louie-py
- Graphistry GitHub org: https://github.com/graphistry
- OpenCode, the open-source coding agent named in the post: https://opencode.ai/ and https://github.com/anomalyco/opencode
- GLM 5.3 Flash is the open-weight model named among the small models (Z.ai; their Sep 23 post calls it open-weight). Weights: https://huggingface.co/zai-org/GLM-5.3-Flash. GPT-5.6 Luna is named as a small OpenAI model; this note does not link a weights page for it.
- Graphistry MCP is not named in this post. Their docs for the visualization MCP, and the separate upload repo: https://hub.graphistry.com/docs/mcp/intro/ and https://github.com/graphistry/graphistry-mcp. Agent skill files they publish: https://github.com/graphistry/graphistry-skills
- Benchmark: https://botsbench.com/ · this comparison: https://botsbench.com/astra-cybt.html · method: https://botsbench.com/methodology.html

## Relation to existing notes

This is the harness question from the Oct 3 agent-harness / Jev cluster, and from the Oct 4 Decision 2.0 and AgentCraft delta: the machinery around the model, measured here on security investigations rather than on coding or decisions. It also sits next to the Oct 5 attack-surface mapping note, which uses OpenCode as the coding agent, and the Oct 7 ProjectDiscovery note, where a poisoned model drives Codex to send a project's `.env` out — this post scores those same coding agents (Codex, Claude Code, OpenCode) as investigation tools and says they still trail Louie.

## Feeds

- Graphistry blog index: https://www.graphistry.com/blog
- Graphistry RSS: https://www.graphistry.com/feed (lastBuildDate on this check: Wed Oct 7 2026 20:17:22 UTC, 3:17pm CT)
- Louie.ai blog / news / changelog: none found. https://louie.ai/blog, https://louie.ai/news, and https://louie.ai/changelog all returned 404. Louie product posts are on the Graphistry blog. The closest dated Louie page is trainings: https://louie.ai/trainings. The Python client changelog file exists and was empty: https://github.com/graphistry/louie-py/blob/main/CHANGELOG.md
- X: Graphistry lists https://twitter.com/graphistry on the PyPI page for `graphistry` (https://pypi.org/project/graphistry/). No separate Louie account turned up. https://x.com/Graphistry returned 403 on this check, so no timeline was read.
- GitHub org: https://github.com/graphistry

**Baseline, Graphistry blog, Oct 7 2026.** Five most recent posts, titles and byline dates as shown on the posts. Feed times are from https://www.graphistry.com/feed, converted to CT (CDT, UTC−5).

1. GPT-6 Astra and Claude Fable 5.1 push the investigation frontier, but coding agents still trail investigation harnesses — https://www.graphistry.com/blog/ai-coding-agents-investigation-harnesses — October 7, 2026 (feed 2:44pm CT)
2. GLM 5.3 Flash the brings open-weight leader’s cost down 80%+ on botsbench — https://www.graphistry.com/blog/glm-5-3-flash-botsbench — September 23, 2026 (feed 5:36pm CT)
3. Graphistry 2.53.0: 10 million edges in 537 MB of browser memory — https://www.graphistry.com/blog/graphistry-2-53-0-large-graph-visualization-at-10-million-edges — September 3, 2026 (feed 3:07pm CT)
4. Botsbench AI security openweight model roundup TL;DR — https://www.graphistry.com/blog/botsbench-ai-security-openweight-model-roundup-tldr — August 7, 2026 (feed 2:29pm CT)
5. Agentic timelining — https://www.graphistry.com/blog/agentic-timelining — July 29, 2026 (feed 5:58pm CT)

**Baseline, Louie.ai blog/news, Oct 7 2026.** No posts. The three URLs above 404, so there is no five-post list to record.

## Later deltas

- 2026-10-21: [2026-10-21-graphistry-delta.md](2026-10-21-graphistry-delta.md) (BSides Augusta 2026 training repo; graphistry-skills graphistry-mcp skill)
- 2026-10-22: [2026-10-22-graphistry-delta.md](2026-10-22-graphistry-delta.md) (BSides Augusta investigation-loop skill; graphistry-skills PR #36 Cypher-first MCP skill, open)
- 2026-10-23: [2026-10-23-graphistry-delta.md](2026-10-23-graphistry-delta.md) (graphistry-skills PR #36 merged, Cypher-only MCP skill; pygraphistry 0.61.x; louie-py fixes)
- 2026-10-26: [2026-10-26-graphistry-delta.md](2026-10-26-graphistry-delta.md) (pygraphistry 0.61.2; hybrid-agent planner/worker skill polling #2229)
- 2026-11-02: [2026-11-02-graphistry-delta.md](2026-11-02-graphistry-delta.md) (@lmeyerov on Louie read-only investigations; pygraphistry #2265 subagent-safe skill filenames)
