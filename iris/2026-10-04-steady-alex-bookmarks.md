# @Steady_Alex bookmark delta, Oct 4 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Oct 4, 2026 morning CT. Baseline is the Oct 3 catalog: [2026-10-03-steady-alex-bookmarks.md](2026-10-03-steady-alex-bookmarks.md).

Oct 5, 2026 pull: eight new bookmarks and the first folders (Moodils, Cyber, Memes; one meme skipped). This note stays the Oct 4 delta. Next: [2026-10-05-steady-alex-bookmarks.md](2026-10-05-steady-alex-bookmarks.md).

## Summary

Access URLs (Hugging Face, API, and signup) were backfilled for the items below, per Alex on Oct 5.

- **Total bookmarks:** 39. The Oct 3 catalog had 35. This pull adds 4.
- **New post ids:** four ids that are not in the Oct 3 table. The other 35 are unchanged.
- **Pagination:** the Oct 3 pull finished on one page (`result_count` 35, no `next_token`, page size 100). This note records the four ids that showed up on the Oct 4 morning pull; it does not replace that catalog.
- **Post dates:** the four new posts run Oct 2, 2026 8:25pm CT through Oct 3, 2026 4:50am CT (created_at, converted from UTC). The full list now runs Sep 13, 2026 1:54pm CT through Oct 3, 2026 4:50am CT. The Oct 3 window was Sep 13 through Oct 1.
- **Folders:** still none. `get_users_bookmark_folders` returned empty, the same result as the two empty calls on Oct 3. No folder ids, so no per-folder bookmark calls. All four new posts are unfoldered, as is the rest of the list.
- **What the delta is:** two harness notes and two launches. Decision 2.0 is an open-weight decision-model family in the Jev / System One niche. AgentCraft is a Minecraft HITL harness. Kolibri-1 is a bilingual Apache MoE. Ming-Image-0.1-Design is a UI and layout image model.

### Topics touched

Counts are new bookmarks only. Oct 3 topic totals stay as written in that file.

- **Agent harnesses, sandboxes, and Jev** — 2 new (Oct 3 had 5)
- **New model launches** — 1 new (Oct 3 had 6)
- **Design and image models** — 1 new. This topic was not in the Oct 3 catalog. The closest prior save is the Qwen-Image GGUF under extreme compression.

## Agent harnesses, sandboxes, and Jev

**2 new bookmarks.** Both sit next to the Oct 3 harness cluster (Jev’s architecture writeup, CLM-8B, Monty, the Cursor harness-cost prompt, Hermes Desktop in a browser). One is weights for structured decisions. The other is a human-in-the-loop UI.

### Decision 2.0

@XunzhuoLiu (Xunzhuo), Oct 2, 2026 8:25pm CT. The vLLM Semantic Router team (vllm-sr) open-sourced Decision 2.0: foundation decision models from about 0.6B to 27B (Kai, Eos, Sol, Nox, Lux, Vega) on Hugging Face under Apache-2.0. They take text or JSON plus a choice, yes-no, or score question and return probabilities in one forward pass, with no text generation. The post is tagged #Jev and sits in the same System One / structured-decision niche as TypeSafe’s Jev. https://x.com/XunzhuoLiu/status/2106193824091681126

**Access:**

- Hugging Face collection: https://huggingface.co/collections/vllm-sr/decision-20
- Weights (Apache-2.0): [Kai-0.6B](https://huggingface.co/vllm-sr/Decision-2.0-Kai-0.6B), [Eos-0.8B](https://huggingface.co/vllm-sr/Decision-2.0-Eos-0.8B), [Sol-2B](https://huggingface.co/vllm-sr/Decision-2.0-Sol-2B), [Nox-4B](https://huggingface.co/vllm-sr/Decision-2.0-Nox-4B), [Lux-9B](https://huggingface.co/vllm-sr/Decision-2.0-Lux-9B), [Vega-27B](https://huggingface.co/vllm-sr/Decision-2.0-Vega-27B).
- No hosted API. The collection lists no inference providers. These are local weights.

### AgentCraft

@BlendiByl (Blendi), Oct 2, 2026 10:34pm CT. AgentCraft is a multi-agent harness presented inside Minecraft. Claude agents plan, work in real git worktrees, and walk over when they need the human. It is a human-in-the-loop UI for orchestration, distinct from older Spigot NPC plugins of the same name. https://x.com/BlendiByl/status/2106226258984264042

Same catalog area as Hermes Desktop-in-browser, Monty, and the Cursor harness-cost prompt. It also sits beside the Oct 3 “agents that build things” cluster. The save is the orchestration UI, not a new builder model.

**Access:**

- Repo: https://github.com/blendi-remade/agentcraft (MIT). The README’s sim backend needs no key.
- Hugging Face: no weights. This is a harness, not a model card.
- Real agents use the Claude Agent SDK. Keys: https://console.anthropic.com · SDK docs: https://code.claude.com/docs/en/agent-sdk/overview

## New model launches

**1 new bookmark.** The Oct 3 launch cluster already has Ling-3.1-flash, Naive-N0.5-Flash, Cloudflare Clef, Space Bunny, and Rysana V2. Kolibri is another open MoE from the same week, with a different license and language pair.

### Kolibri-1

@Aleph__Alpha (Aleph Alpha), Oct 3, 2026 3:54am CT. Aleph Alpha released Kolibri-1 on German Unity Day: an English/German mixture-of-experts, 78.1B total and 3.46B active, native context about 262k and extensible to 1M, with reasoning and tool calling. Apache 2.0 weights are on Hugging Face. It needs about 78GB in FP8; a practical minimum is roughly two A100 80GB cards or one H200-class GPU. The pitch is sovereign European use in public administration and industry. https://x.com/Aleph__Alpha/status/2106306840657297814

Another open MoE in the same week as Ling-3.1-flash and Naive-N0.5-Flash, already in the Oct 3 catalog. The difference is bilingual German/English and Apache weights, rather than a stealth API model.

**Access:**

- Weights (Apache 2.0): https://huggingface.co/Aleph-Alpha/Kolibri-1 (FP8) · BF16: https://huggingface.co/Aleph-Alpha/Kolibri-1-BF16
- Product page: https://aleph-alpha.com/en/kolibri/ · blog: https://aleph-alpha.com/en/blog/kolibri-has-landed-a-sovereign-open-weight-model/ · tech report: https://aleph-alpha.com/downloads/tech-report.pdf
- vLLM plugin named in the blog: https://github.com/Aleph-Alpha/aleph-alpha-inference
- No public Kolibri API or signup on the product page or the blog. They describe on-prem weights.

## Design and image models

**1 new bookmark.** New topic for this delta. Oct 3 saved Qwen-Image as GGUFs under extreme compression (text encoder in system RAM, image weights in VRAM). Ming-Image is a UI, mockup, and layout model.

### Ming-Image-0.1-Design

@laowangbabababa (产品经理老王霸), Oct 3, 2026 4:50am CT. A Chinese writeup of Ant Ling / inclusionAI Ming-Image-0.1-Design: a design-focused text-to-image model of about 6B (UI, posters, infographics), MIT licensed, and ranked #1 open-weight on the Artificial Analysis UI/UX Design slice (about 1082 Elo). A companion Layer model splits designs into editable RGBA layers. “6B” is the DiT; the full BF16 package is about 53GB, roughly a 26B-equivalent once the text encoder is counted. https://x.com/laowangbabababa/status/2106321081393176741

Alex’s catalog already had Qwen-Image GGUFs for local image. This is the layout and mockup model.

**Access:**

- Weights (MIT): https://huggingface.co/inclusionAI/Ming-Image-0.1-Design
- Layer model (RGBA split): https://huggingface.co/inclusionAI/Ming-Image-0.1-Design-Layer
- Inference repo: https://github.com/inclusionAI/Ming-Image
- OpenRouter: https://openrouter.ai/inclusionai/ming-image-0.1-design · layer: https://openrouter.ai/inclusionai/ming-image-0.1-design-layer

## New bookmarks

Numbers 36–39 continue the Oct 3 table so the full set reads 1–39. They are lookup ids for this delta. The Oct 3 table is not renumbered, and these four rows are not a claim about bookmark-API order among the new saves.

| # | Author | Posted (CT) | Topic | Post |
|---|---|---|---|---|
| 36 | @XunzhuoLiu | Oct 2, 2026 8:25pm CT | Agent harnesses, sandboxes, and Jev | [2106193824091681126](https://x.com/XunzhuoLiu/status/2106193824091681126) |
| 37 | @Aleph__Alpha | Oct 3, 2026 3:54am CT | New model launches | [2106306840657297814](https://x.com/Aleph__Alpha/status/2106306840657297814) |
| 38 | @laowangbabababa | Oct 3, 2026 4:50am CT | Design and image models | [2106321081393176741](https://x.com/laowangbabababa/status/2106321081393176741) |
| 39 | @BlendiByl | Oct 2, 2026 10:34pm CT | Agent harnesses, sandboxes, and Jev | [2106226258984264042](https://x.com/BlendiByl/status/2106226258984264042) |
