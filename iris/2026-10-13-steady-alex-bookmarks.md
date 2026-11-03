# @Steady_Alex bookmark scan, Oct 13 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Tue Oct 13, 2026 ~9:33am CT. Baseline: [Oct 12 delta](2026-10-12-steady-alex-bookmarks.md) (75 total) on main.

## Summary

- **Total bookmarks:** 76 (one page, `result_count` 76, no `next_token`, page size 100).
- **New vs Oct 12 baseline:** 1 id. All 75 baseline ids still present.
- **Memes skipped:** none new (Memes folder still holds 2108663800102609008 and 2107021822155985254).
- **Folders:** no new folders. Moodils now has 15; Cool tech to try 12; Keep an eye on this 5; Cyber 2; Memes 2 (Memes, Moodils, Cool tech to try, Keep an eye on this, Cyber).

## Moodils

### MiniCPM-V 4.7 — OpenBMB open-source on-device MLLM series (35B-A3B MoE + 1B)

@OpenBMB, posted Oct 12 12:15pm CT (note tweet). OpenBMB / ModelBest released **MiniCPM-V 4.7**, the latest MiniCPM-V multimodal series for single-image, multi-image, and video understanding with on-device focus. Two primary checkpoints: **MiniCPM-V-4.7-35B-A3B** (first MoE in the MiniCPM-V series; ~35.2B params per HF; name encodes 35B total / A3B active) and **MiniCPM-V-4.7-1B** (dense; ~1.55B params / BF16). Introduces Lookahead Expert Scheduling (LES) for on-device MoE; mixed 4×/16× visual token compression; Self-Replay Fine-Tuning (SRFT). Language backbone credited to Qwen3.5 / Qwen3.6; vision module to SigLIP2. HF model cards and docs dated Oct 12 2026 (weights repos created Oct 6–7 2026; documentation pass Oct 12).
https://x.com/OpenBMB/status/2109694573408866351

**Access:**

- HF collection: https://huggingface.co/collections/openbmb/minicpm-v-47
- Flagship MoE: https://huggingface.co/openbmb/MiniCPM-V-4.7-35B-A3B (~70.6 GB BF16 shard tree)
- Dense 1B: https://huggingface.co/openbmb/MiniCPM-V-4.7-1B
- Quant / draft variants (same collection): `…-35B-A3B-gguf`, `…-1B-gguf`, `…-35B-A3B-FP8`, `…-35B-A3B-AWQ`, `…-35B-A3B-GPTQ`, `…-35B-A3B-int4`, `…-35B-A3B-DSpark`, `…-1B-AWQ`, `…-1B-GPTQ`, `…-1B-int4`, `…-1B-DSpark`
- ModelScope mirrors listed on the cards (e.g. https://modelscope.cn/models/OpenBMB/MiniCPM-V-4.7-35B-A3B)
- Docs / code: https://github.com/OpenBMB/MiniCPM-V · English series note https://github.com/OpenBMB/MiniCPM-o/blob/main/docs/minicpm_v4dot7_en.md · LES / on-device stack https://github.com/OpenBMB/llama.cpp-omni · Edge apps https://github.com/OpenBMB/MiniCPM-V-Apps · Cookbook https://github.com/OpenSQZ/MiniCPM-V-CookBook/blob/main/docs/pages/v4.7/overview.md
- Live demo: https://huggingface.co/spaces/openbmb/MiniCPM-V-4.7-Demo
- Hosted API (ModelBest): docs https://github.com/OpenBMB/MiniCPM-o/blob/main/docs/api.md · base `https://api.modelbest.cn/v1` · signup https://platform.modelbest.cn · model ids `MiniCPM-V-4.7-1B`, `MiniCPM-V-4.7-35B-A3B`
- SRFT blog: https://openbmb.cn/en/blog/self-replay-fine-tuning
- License: Apache-2.0 (HF card front matter + GitHub `OpenBMB/MiniCPM-V`); `llama.cpp-omni` is MIT
- Hardware (publisher claims): on-device path for 35B-A3B with LES + layer-wise quant + DSpark — 13+ tok/s at ~3 GB memory on iPhone 17 Pro Max; 17+ tok/s on iPad Pro M4 (16 GB). Platforms named: iOS, Android, HarmonyOS; day-0 chip notes for Rockchip, Houmo, Intel, AMD, Arm. Server path: Transformers ≥5.18, SGLang, vLLM, llama.cpp, Ollama; OpenVINO day-0 for Intel.

## Skipped (Memes)

- None new. Memes folder unchanged: 2108663800102609008, 2107021822155985254.
