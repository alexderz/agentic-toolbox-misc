# @Steady_Alex bookmark scan, Nov 5 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Thu Nov 5, 2026 ~7:52pm CT. Baseline: [Nov 3 scan](2026-11-03-steady-alex-bookmarks.md) (ids through `2117728424978715116` and earlier same-day notes; prior Nov 5 daytime runs had no new ids).

## Summary

- **New vs baseline:** 2 ids on page 1 (both above the prior top id `2117728424978715116`).
- **Memes skipped:** none (Memes folder unchanged, 2 items).
- **Folders:** unchanged (Moodils, Cool tech to try, tech updates, Keep an eye on this, Memes, Cyber). Cool tech to try +2.

## Cool tech to try

### Ripple-65B Preview (Ricursive Intelligence)
@TeksEdge, Nov 4 8:26pm CT. https://x.com/TeksEdge/status/2118168112759734458
- **What it is:** 65B dense Transformer open-weight model from Ricursive Intelligence (`ricursiveAI`), pretrained from scratch on 12T predominantly-English and code tokens, with reported support up to 1M context. Architecture: thin-and-deep (d_model 5120, 80 layers), Gemma 3N–like layout with overprovisioned attention heads, higher SWA-to-global ratio, FFN activation clipping, gated attention, global NoPE, and value residuals. Preview release includes BF16 instruct, NVFP4 instruct (MLP in NVFP4, attention kept BF16), BF16 base, and a DFlash2 speculative draft model. Official card reports Terminal-Bench 2.1 80.5 / 80.52 (self-reported and Terminus 2), and compares against larger US open-weight MoE models (Reflection Beam 501B, Meta Muse Spark Open 816B, Thinking Machines Inkling 975B, Nemotron 3 Ultra 550B). Company page states full R&D cost $32M and availability on Hugging Face, Together AI, GMI Cloud, OpenRouter, and Fireworks.
- **License:** Apache-2.0.
- **Size and hardware:** BF16 instruct ~64.78B params (HF safetensors count). NVFP4 instruct HF param count ~39.6B mixed. DFlash2 draft ~4.04B BF16. Card: fits NVIDIA DGX Spark–class hardware; 250 tok/s on 2×B200 batch=8 before quantization/custom kernels. Community GGUF (AtomicChat): e.g. AD-IQ2_XXS ~20.0 GB, Q4_K_M ~38.8 GB. Post notes a custom llama.cpp build until Ripple support is merged (`akhaliq/llama-cpp-ricursive-cuda120` exists on HF as a related listing).
- **Release:** HF instruct repo created Nov 3 2026 8:41pm CT (2026-11-04T02:41:21Z); NVFP4 and DFlash2 Nov 4 2026; base repo created Oct 14 2026. Citation year 2026, Ricursive Intelligence.
- **Links:** https://www.ricursive.com/ripple · https://huggingface.co/ricursiveAI/Ripple-65B-Preview · https://huggingface.co/ricursiveAI/Ripple-65B-Preview-NVFP4 · https://huggingface.co/ricursiveAI/Ripple-65B-Base-Preview · https://huggingface.co/ricursiveAI/Ripple-65B-Preview-DFlash2 · GGUF https://huggingface.co/AtomicChat/Ripple-65B-Preview-GGUF · OpenRouter https://openrouter.ai/ricursiveai/ripple-65b-preview (context 1,048,576; listed price $0.20 / $0.60 per M prompt/completion tokens, cache read $0.05 per M)

### Hyperkernel / Hyperserve (Hyperstition)
@hyperstition_cc, Nov 5 1:56pm CT. https://x.com/hyperstition_cc/status/2118432349352595528
- **What it is:** first public release of megakernels produced by Hyperkernel, Hyperstition’s recursive megakernel generator. The open GitHub repo is named Hyperserve and ships Alpha Rust binaries that run those generated megakernels (OpenAI-compatible LLM server, openpilot drive, Evo 2 DNA, Matrix-Game world model). Post: generator built ~20 days earlier for internal use; this release opens the megakernels; full Hyperkernel stack and Kimi/GLM serving stack stated for the following weeks. Post lists target domains (DeepSeek / Kimi / GLM inference, Qwen pretraining, hardware fault recovery, robotics π₀-FAST / ACT, Matrix-Game, OpenPilot, Moshi, Evo 2, ESMFold) and reports DeepSeek v4.1 Flash low-latency decode figures vs NVIDIA-published vLLM numbers. Primary hardware in the post: NVIDIA B300 (generation said to extend to B200, AMD, TPU).
- **License:** MIT.
- **Size and hardware (repo README):** current megakernels compiled for NVIDIA B300 — 4 GPUs for LLMs, 1 for driving and DNA, 2 for world models; LLMs need ~203 GB host RAM for Engram tables. Build requires Rust (`rust-toolchain.toml`) and NVIDIA driver R580+. Model checkpoints are not included; user supplies safetensors (e.g. `deepseek-ai/DeepSeek-V4.1-Flash` at revision `314113f8a7dadb388215396ba5fbee2c610a04d6`, openpilot v0.11.2 driving model, `arcinstitute/evo2_7b`, `Skywork/Matrix-Game-3.0`).
- **Release:** GitHub repo created Nov 5 2026 1:44pm CT (2026-11-05T19:44:46Z); last push Nov 5 2026 ~4:44pm CT. Site https://hyperstition.cc/.
- **Links:** https://github.com/Hyperstitioncc/Hyperkernel · https://hyperstition.cc/
