# @Steady_Alex bookmark scan, Oct 14 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Wed Oct 14, 2026 ~9:15am CT. Baseline: [Oct 13 delta](2026-10-13-steady-alex-bookmarks.md) (76 total) on main.

## Summary

- **Total bookmarks:** 79 (one page, `result_count` 79, no `next_token`, page size 100).
- **New vs Oct 13 baseline:** 3 ids. All 76 baseline ids still present.
- **Memes skipped:** none new (Memes folder still holds 2108663800102609008 and 2107021822155985254).
- **Folders:** no new folders. Moodils now has 16; Cool tech to try 14; Keep an eye on this 5; Cyber 2; Memes 2 (Memes, Moodils, Cool tech to try, Keep an eye on this, Cyber).

## Moodils

### LFM2.5-24B-A2B — Liquid AI largest LFM2.5 MoE (24B / 2B active)

@liquidai, posted Oct 13 12:11pm CT. Liquid AI released **LFM2.5-24B-A2B**, the largest and final member of the LFM2.5 family (family spans LFM2.5-230M through LFM2.5-24B-A2B). Open-weight hybrid MoE reasoning model: **24B total parameters**, **~2.45B active per token** (64 experts/block, top-4), **131K context**, **128K vocabulary**, pre-training scaled to ~33T tokens (mid-training + post-training bring the published training budget to 36T on the HF card). Reasoning-only (always thinks before answering); post-trained for tool calling and multi-step agentic workloads inside harnesses named in the blog (OpenClaw, Hermes Agent, Pi, OpenCode). Builds on LFM2-24B-A2B with context 32K→131K and vocab 65K→128K. Blog and HF dated Oct 13 2026.
https://x.com/liquidai/status/2110055807194931348

**Access:**

- Blog: https://www.liquid.ai/blog/lfm2-5-24b-a2b
- Docs: https://docs.liquid.ai/lfm/models/lfm25-24b-a2b
- HF collection: https://huggingface.co/collections/LiquidAI/lfm25
- Post-trained: https://huggingface.co/LiquidAI/LFM2.5-24B-A2B
- Base: https://huggingface.co/LiquidAI/LFM2.5-24B-A2B-Base
- Variants: https://huggingface.co/LiquidAI/LFM2.5-24B-A2B-GGUF · https://huggingface.co/LiquidAI/LFM2.5-24B-A2B-FP8 · https://huggingface.co/LiquidAI/LFM2.5-24B-A2B-ONNX · MLX https://huggingface.co/LiquidAI/LFM2.5-24B-A2B-MLX-4bit (also MLX-5bit, MLX-6bit, MLX-8bit, MLX-bf16)
- HF companion blog: https://huggingface.co/blog/LiquidAI/lfm25-24b-a2b
- Playground: https://playground.liquid.ai/
- Hosted API (Liquid Console): https://console.liquid.ai/ · OpenAI-compatible `https://api.liquid.ai/v1` · model id `LFM2.5-24B-A2B` · blog pricing $0.10/1M input ($0.05 cached), $1.00/1M output; new Console signup noted as $2 credit
- License: LFM Open License v1.0 (Apache-2.0-based; free commercial use conditioned on under $10M USD annual revenue) — https://www.liquid.ai/lfm-license · guide https://docs.liquid.ai/lfm/help/model-license · LICENSE on HF card
- Hardware (publisher claims): edge decode 184 tok/s on Apple M5 Max and 114 tok/s on AMD Ryzen AI Max+ 395 (llama.cpp Q4_K_M, 4K input, Pipette); up to ~21K output tok/s on one NVIDIA B300 (SGLang 0.5.22, BF16). Day-one stacks named: Transformers ≥5.0, vLLM, SGLang, llama.cpp, MLX (`mlx-lm>=0.32.0`), ONNX, LM Studio.

## Cool tech to try

### DigUp — macOS menu bar semantic search (EmbeddingGemma 2, on-device)

@googlegemma, posted Oct 13 11:25am CT. **DigUp** is an open-source macOS menu bar app by Abdur Rahim (`ARahim3`) that runs Google DeepMind’s **EmbeddingGemma 2** locally for multimodal semantic search over user-chosen folders (photos, PDFs/docs, audio, video, optional code). Natural-language queries; opens video/audio at the matched moment and PDFs at the matched page. First public release **v0.6.0** Oct 9 2026; latest **v0.6.1** published Oct 12 2026 11:20am CT. Gemma account post is Oct 13.
https://x.com/googlegemma/status/2110044337849692644

**Access:**

- GitHub: https://github.com/ARahim3/DigUp
- Releases / DMG: https://github.com/ARahim3/DigUp/releases · latest https://github.com/ARahim3/DigUp/releases/tag/v0.6.1 · asset `DigUp-0.6.1.dmg`
- Homebrew cask (README): `brew install --cask arahim3/tap/digup`
- Embedding model: https://huggingface.co/google/embeddinggemma-2 (740M params; Apache 2.0 per DigUp README)
- License: MIT (repo LICENSE; DigUp README). Dependencies called out in README: EmbeddingGemma 2 Apache 2.0, llama.cpp MIT, Sparkle MIT
- Hardware / platform: Apple Silicon Mac, macOS 14 or later (tested on macOS 26 per README). Model download once ~865 MB (text ~310 MB + image/audio encoders ~555 MB); app ~20 MB. Runs ggml-org 8-bit EmbeddingGemma 2 via llama.cpp on Metal; no account/API key. Global shortcut ⇧⌘Space.

### Constrained Decoding Models (CDMs) — ScaleDown Classify / Extract / Summarize (+ Compress)

@neal_k_patel, posted Oct 13 7:04am CT. ScaleDown (Neal Patel) introduced **Constrained Decoding Models (CDMs)**: task-specific models that read input once and return constrained structured answers rather than open-ended token-by-token generation. Launch lineup on the product site: **Classify**, **Extract**, **Summarize**, plus **Compress** (query-aware context compression). Hosted API; docs describe Classify (label/rubric probabilities), Extract (schema-driven structured fields, OpenAI-compatible chat completions), Summarize, Compress, and a Jev-compatible Decisions API. Product page states 1M-token multimodal context for the task models; new accounts get 50M free tokens.
https://x.com/neal_k_patel/status/2109978626124898587

**Access:**

- Product: https://www.scaledown.ai/
- Docs: https://docs.scaledown.ai/introduction · quickstart https://docs.scaledown.ai/quickstart
- API base: `https://api.scaledown.xyz` (docs note `api.scaledown.ai` is not an API host) · auth via `x-api-key`
- Model docs: Classify https://docs.scaledown.ai/api-reference/classify · Extract https://docs.scaledown.ai/api-reference/extract · Summarize https://docs.scaledown.ai/api-reference/summarize · Compress https://docs.scaledown.ai/api-reference/compress · Decisions (Jev-compatible) https://docs.scaledown.ai/api-reference/decisions
- Login / signup: https://www.scaledown.ai/ (site “LOGIN / SIGN UP” / “GET API KEY”; docs also point to sales for keys)
- Pricing (product page table, Oct 2026): Classify / Extract / Summarize text input $0.05/1M tokens, image input $0.15/1M tokens, output free, 1M context; Compress text $0.05/1M, output free, 1M context. Enterprise dedicated/self-host quote path on the same page.
- License / distribution: hosted SaaS (not an open-weight model release). Self-hosted / dedicated instance offered as Enterprise on the pricing section.

## Skipped (Memes)

- None new. Memes folder unchanged: 2108663800102609008, 2107021822155985254.
