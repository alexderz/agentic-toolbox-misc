# @Steady_Alex bookmark scan, Oct 12 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Mon Oct 12, 2026 ~9:40am CT. Baseline: [Oct 11 delta](2026-10-11-steady-alex-bookmarks.md) (66 total) on main.

## Summary

- **Total bookmarks:** 75 (one page, `result_count` 75, no `next_token`, page size 100).
- **New vs Oct 11 baseline:** 9 ids. All 66 baseline ids still present.
- **Memes skipped:** none new (Memes folder still holds 2108663800102609008 and the Oct 5 skip 2107021822155985254).
- **Folders:** no new folders. Cool tech to try now has 12; Moodils now has 14; Keep an eye on this now has 5; Cyber and Memes unchanged (Memes, Moodils, Cool tech to try, Keep an eye on this, Cyber).

## Cool tech to try

### NVIDIA PersonaPlex-7B — open full-duplex speech-to-speech (voice + role)

@oliviscusAI, posted Oct 11 6:30am CT. NVIDIA open-sourced **PersonaPlex-7B** (v1): full-duplex conversational speech model that listens and speaks concurrently via a dual-stream architecture (Moshi / Moshiko lineage). Conditioned on a voice prompt plus a text role/scenario prompt. Gated HF weights under NVIDIA Open Model License; code MIT. Project page + paper available. Continuity with other local voice / Nemotron speech bookmarks.
https://x.com/oliviscusAI/status/2109245289798549819

**Access:**

- HF (official, gated): https://huggingface.co/nvidia/personaplex-7b-v1
- Code: https://github.com/NVIDIA/personaplex
- Project / demo page: https://research.nvidia.com/labs/adlr/personaplex/
- Paper: https://arxiv.org/abs/2602.06053
- Accept NVIDIA Open Model License on the HF card; needs `HF_TOKEN`. Real-time path: ~24 GB+ VRAM (Linux + CUDA). No separate paid PersonaPlex API called out in the announcement.

### ManimGX — fast 3D animation engine for coding agents (Manim CE API)

@sinaatalay (Academa), posted Oct 10 5:18pm CT. Open-source Rust + wgpu animation engine aimed at agents: Manim Community Edition–compatible Python API, claims ~90× faster than ManimCE on their M4 Pro bench, `pip install manimgx`, browser path via WebGPU, `manimgx inspect` for agent layout feedback. Docs + llms.txt prompt for one-shot agent install/render.
https://x.com/sinaatalay/status/2109045945149395421

**Access:**

- Source: https://github.com/academa-labs/manimgx
- Docs / quickstart: https://manimgx.academa.ai · https://manimgx.academa.ai/user-guide/quickstart/
- Agent prompt seed: https://manimgx.academa.ai/llms.txt
- PyPI: https://pypi.org/project/manimgx/ (v0.1.0 noted Oct 7 2026)
- Not a foundation model; no HF weights. MIT (and bundled third-party licenses per package metadata).

### REA — Reverse Engineer Anything (MCP for agents over binaries / apps)

@RoundtableSpace, posted Oct 11 1:15am CT. Open-source MCP + CLI (**REA**) that lets Claude Code / Codex / Cursor-class agents inspect native binaries, Electron apps, websites, APKs, firmware, and EVM bytecode with evidence-backed claims, then help reconstruct features. Wraps Hopper / Ghidra / IDA / JADX-style providers rather than shipping its own decompiler. Setup via `npx rea-agents@latest setup`.
https://x.com/RoundtableSpace/status/2109165852578992582

**Access:**

- Source: https://github.com/morluto/rea
- Docs / get started: https://morluto.github.io/rea/ · https://morluto.github.io/rea/get-started/
- MCP client notes: https://rea.run/docs/mcp-clients/
- npm package runner: `npx rea-agents@latest setup` / `doctor`
- Not a model; no HF card. MIT. Needs Node and (for deep native analysis) a local Hopper/Ghidra/IDA provider.

### Agent SVG comparison — clockwork orrery prompt (Brjen)

@Brjen, posted Oct 11 11:52am CT (reply tagging @Steady_Alex). Same complex animated-SVG prompt (brass clockwork orrery with real relative planet speeds, meshing gears, day/night shadows) run across models in their agent environment; outputs assembled into a comparison video. Not a new model release — a capability / harness comparison bookmark.
https://x.com/Brjen/status/2109326324649369859

**Access:**

- No new model cards or repos in the post. Comparison artifact is the in-thread video.

## Moodils

### Project Maya speed follow-ups — GLM-5.3-Flash on 3090 + 64 GB (Ajay + Maya)

@ItsmeAjayKV, two posts Oct 11 (6:23am and 2:07pm CT). Continues Oct 9 Project Maya bookmark. Claims large speedups serving **GLM-5.3-Flash** through Project Maya on a single RTX 3090 + 64 GB RAM; second post cites his own hand-mixed **AJ-IQ2_XXS** GGUF at ~22–24 tok/s gen and ~910–1150 t/s prefill (8k/32k) after Maya engine work / in-progress PR. Same 321B MoE / local-offload theme.
https://x.com/ItsmeAjayKV/status/2109243568925880542  
https://x.com/ItsmeAjayKV/status/2109360177598321095

**Access:**

- Project / engine (unchanged): https://github.com/mw00/project-maya
- Official Maya GGUFs: https://huggingface.co/peasantsmith/GLM-5.3-Flash-Maya-GGUF
- Base model (official): https://huggingface.co/zai-org/GLM-5.3-Flash
- Community hand-mixed GGUF referenced in the speed posts: https://huggingface.co/aj9o9/GLM-5.3-Flash-GGUF (AJ-IQ2_XXS ~87 GB; AJ-IQ3_XXS ~112 GB) — **not** official Z.ai / PeasantSmith; needs recent llama.cpp (author cites unmerged PR #27752)
- No paid API required for local Maya. MIT on base; community quant is third-party.

### DeepSeek V4.1 Flash UNCENSORED (dealignai) — abliterated third-party fork

@k2sbhai, posted Oct 11 7:17am CT. Points at a community **UNCENSORED / abliterated** FP8 build of DeepSeek-V4.1-Flash (552B backbone, 8B/16B active, 1M context, vision) under MIT claims. This is **not** a DeepSeek release — weight-level refusal removal by `dealignai`. The Oct 7 note records ProjectDiscovery's write-up on abliterated weights.
https://x.com/k2sbhai/status/2109257180868461030

**Access:**

- Official base: https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash
- Bookmark target (third-party abliterated): https://huggingface.co/dealignai/DeepSeek-V4.1-Flash-UNCENSORED-FP8
- Other community abliterated variants also exist (e.g. `distributedcognition/…`).
- Hosted DeepSeek API (official product line, separate from this fork): https://platform.deepseek.com
- Serving the official line still needs recent SGLang / DeepSeek reference stacks; the uncensored card documents SGLang `dev-dsv41` paths.

### vLLM congrats — Decision 3.0 open weights (secondary to Oct 11)

@vllm_project, posted Oct 11 4:11am CT. Official vLLM account congratulating the vllm-sr team on Decision 3.0 / multimodal Jev open weights. Quote-tweet of the Oct 11 Decision 3.0 bookmark already filed; no new model cards beyond that release.
https://x.com/vllm_project/status/2109210324985622960

**Access:**

- Same as Oct 11 Decision 3.0 note: HF collection https://huggingface.co/collections/vllm-sr/decision-30 · flagship https://huggingface.co/vllm-sr/d3 · project https://vllm-sr.ai · semantic-router https://github.com/vllm-project/semantic-router

## Keep an eye on this

### Qwen 3.8 Flash Next vs 27B quant comparison (IQ3_S / IQ3_XXS / UD-Q4_K_XL)

@Brjen, posted Oct 10 9:13pm CT. Same-prompt video comparison of three local quants: Qwen 3.8 Flash Next IQ3_S, Flash Next IQ3_XXS, and Qwen 3.8 27B UD-Q4_K_XL. No new base weights announced.
https://x.com/Brjen/status/2109105176460071314

**Access:**

- Official bases: https://huggingface.co/Qwen/Qwen3.8-Flash-Next · https://huggingface.co/Qwen/Qwen3.8-27B
- Product / chat: https://chat.qwen.ai · Model Studio https://www.alibabacloud.com/help/en/model-studio/
- Community GGUF / UD quants vary by uploader.

## Skipped (Memes)

- None new. Memes folder unchanged: 2108663800102609008, 2107021822155985254.
