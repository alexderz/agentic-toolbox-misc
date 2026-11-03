# @Steady_Alex bookmark scan, Oct 11 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Sun Oct 11, 2026 ~9:15am CT. Baseline: [Oct 10 delta](2026-10-10-steady-alex-bookmarks.md) (62 total) on main.

## Summary

- **Total bookmarks:** 66 (one page, `result_count` 66, no `next_token`, page size 100).
- **New vs Oct 10 baseline:** 4 ids. All 62 baseline ids still present.
- **Memes skipped:** none new (Memes folder still holds 2108663800102609008 and the Oct 5 skip 2107021822155985254).
- **Folders:** no new folders. Cool tech to try now has 8; Moodils now has 10; Keep an eye on this now has 4; Cyber and Memes unchanged (Memes, Moodils, Cool tech to try, Keep an eye on this, Cyber).

## Moodils

### Decision 3.0 — open multimodal foundation decision models (d3 family)

@XunzhuoLiu (vLLM Semantic Router / Decision), posted Oct 11 3:59am CT. Follow-up to Decision 2.0 (Oct 4 catalog / Oct 3 Decision 2.0 bookmark). Decision 3.0 is multimodal: text or JSON plus optional images and videos, returning Choice / Yes-No / Score probabilities in one call without generating text. Headline model **d3** (~26.09B incl. 0.46B vision encoder, built on Qwen3.8-27B, Apache-2.0) claims #1 on both Jev Decision Index boards in their eval (text Index ~64.7; vision Index ~71.6) and a new Pareto frontier vs Decision 2.0 / Jev / peers. Collection spans 0.6B–27B: d3, d3-flash (~8B), d3-mini (~5B), d3-nano (~2B), d3-lite (~0.9B), d3-edge (~0.6B).
https://x.com/XunzhuoLiu/status/2109207207284027737

**Access:**

- HF collection (official): https://huggingface.co/collections/vllm-sr/decision-30
- Flagship: https://huggingface.co/vllm-sr/d3
- Smaller sizes: https://huggingface.co/vllm-sr/d3-flash · https://huggingface.co/vllm-sr/d3-mini · https://huggingface.co/vllm-sr/d3-nano · https://huggingface.co/vllm-sr/d3-lite · https://huggingface.co/vllm-sr/d3-edge
- Project / docs: https://vllm-sr.ai · semantic-router source https://github.com/vllm-project/semantic-router
- Base weights lineage: https://huggingface.co/Qwen/Qwen3.8-27B
- No separate hosted Decision-3.0 paid API called out in the announcement; load via Transformers `AutoModel.from_pretrained("vllm-sr/d3", trust_remote_code=True)` (or the `decision` pipeline). Apache-2.0.

## Cool tech to try

### exllamav3 1.6.x + DFlash2 — faster local Qwen3.8-27B on 16 GB+ NVIDIA

@MiaAI_lab, posted Oct 10 9:18am CT. Continues the consumer-GPU Qwen3.8-27B cluster (MiaAI 16 GB kits, EXL3 quants, speculative decoding). Credits a PR from @niklaslenz_ai: serve stack moved to **exllamav3 1.6.0**, swapping the MTP draft head for a **DFlash2** draft model; RTX 5090 speed charts linked in-thread. Upstream turboderp ExLlamaV3 added DFlash2 in v1.5.1 and shipped 1.6.0 (Oct 7) / 1.6.1 (Oct 10) with further drafting/VRAM fixes. Same Qwen3.8-27B weights; change is serve/draft path, not a new base model.
https://x.com/MiaAI_lab/status/2108925156601053255

**Access:**

- Upstream engine / releases: https://github.com/turboderp-org/exllamav3 · https://github.com/turboderp-org/exllamav3/releases (v1.6.1 current as of this scan)
- Base model (official): https://huggingface.co/Qwen/Qwen3.8-27B
- MiaAI DFlash2 EXL3 draft quant: https://huggingface.co/Mia-AiLab/Qwen3.8-27B-DFlash2-EXL3-5.0bpw
- MiaAI 16 GB one-click kit (broader EXL3 serve path): https://github.com/MiaAI-Lab/Qwen3.8-27B-16gb-NVIDIA-GPUs-one-click-install
- DFlash2 upstream draft lineage (bf16): often referenced as inco.ai / z-lab Qwen3.8-27B-DFlash2
- No paid API required for local EXL3; OpenAI-compatible local serve from the kits.

## Keep an eye on this

### QwenDevs: "let's do both" — open-weights tease (Qwen4-27 + Max?)

@QwenDevs, posted Oct 10 2:49am CT. Two-word reply ("alright guys, let's do both!") with no links. Secondary coverage reads it as affirming a simultaneous open-weight drop of **Qwen4-27** and **Qwen4-Max** (rumor thread, not an Alibaba press release). No model cards, HF repos, API ids, or dates in the post itself. Foldered under Keep an eye on this.
https://x.com/QwenDevs/status/2108827211524608114

**Access:**

- Official Qwen / Alibaba stance as of Apsara (Sep 22 2026): Qwen 4 is **in training** — press release https://www.alibabacloud.com/en/press-room/alibaba-unveils-roadmap-on-full-stack-ai-strategy?_p_lc=1 (no release date, pricing, or weights).
- Current open line: https://huggingface.co/Qwen (e.g. Qwen3.8-27B, Qwen3.8-Flash-Next) · product/chat https://chat.qwen.ai · cloud API https://www.alibabacloud.com/help/en/model-studio/
- No Qwen 4 HF collection or Model Studio SKU found as of this scan.

### Qwen 4 four-tier lineup rumor (Max / Flash / Plus / 27B)

@leo114119, posted Oct 10 7:19am CT. Chinese-language rumor post listing four simultaneous Qwen 4 tiers — Max (vs Claude Opus class), Flash (vs DeepSeek V4.1 Flash class), Plus ("volume" tier), and 27B (local-deploy favorite) — with a screenshot. Matches attendee/Apsara-stage naming reported elsewhere; **not** in Alibaba's official Sep 22 press release. No weights, API names, or dates. Foldered under Keep an eye on this.
https://x.com/leo114119/status/2108895067935236173

**Access:**

- Official: Qwen 4 still "in training" per Alibaba Apsara press release (link above). Roadmap mentions Qwen 4.5 / Qwen 5 at 5–10T params later — no SKUs yet.
- Architecture preview already open (not Qwen 4 itself): https://huggingface.co/Qwen/Qwen3.8-Flash-Next
- Hosted Qwen 3.8 line: Model Studio / Qwen Cloud docs via https://www.alibabacloud.com/help/en/model-studio/ · chat https://chat.qwen.ai
- No official Qwen 4 Max/Flash/Plus/27B model cards or signup pages as of this scan.
