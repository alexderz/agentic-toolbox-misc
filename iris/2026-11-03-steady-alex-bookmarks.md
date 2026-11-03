# @Steady_Alex bookmark scan, Nov 3 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Tue Nov 3, 2026 ~9:20am CT. Baseline: [Nov 2 scan](2026-11-02-steady-alex-bookmarks.md) (145 total).

## Summary

- **New vs baseline:** 6 ids (all above the Nov 2 set on page 1).
- **Total:** 151 if no baseline ids were removed.
- **Memes skipped:** none (Memes folder unchanged, 2 items).
- **Folders:** no new folders (still Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). Moodils +5, Keep an eye on this +1.

## Moodils

### DeepSeek-V4.1-Flash-1017-obliterated (OBLITERATUS / Pliny)
@elder_plinius, Oct 31 10:21pm CT ("Happy Halloween!"). https://x.com/elder_plinius/status/2116732431491621144
- **What it is:** refusal-direction ablated DeepSeek-V4.1-Flash-1017, made with the OBLITERATUS tool using the failspy method. Card results: refusal rate 4% (2 of 50 eval prompts), KL divergence 0.1305 nats vs original, coherence 100%, capability 6/6 checks. On the 842-prompt OBLITERATUS corpus (838 compared), full refusals 81.62% (original) vs 4.30% (ablated).
- **License:** MIT (weights). OBLITERATUS tool repo is AGPL-3.0.
- **Size:** BF16 safetensors, ~754.6B params, 83 shards, ~1.51 TB total. Transformers library tag.
- **Release:** HF repo created Oct 23 2026, last modified Oct 30 2026.
- **Links:** https://huggingface.co/OBLITERATUS/DeepSeek-V4.1-Flash-1017-obliterated · tool https://github.com/elder-plinius/OBLITERATUS · base https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017

### LFM3-1.7B-abliterated (OrcaRouter)
@OrcaRouter, Nov 2 4:23am CT. https://x.com/OrcaRouter/status/2117200982740508787
- **What it is:** abliterated version of Liquid AI LFM3-1.7B (family facts in [Oct 29 scan](2026-10-29-steady-alex-bookmarks.md)). Post: "Built for local agents and edge AI."
- **License:** other, `lfm1.0` (Liquid AI LFM Open License).
- **Size:** 1.73B params, single BF16 safetensors 3.46 GB; ships custom LFM3 modeling code (Transformers).
- **Release:** HF repo created Nov 2 2026 4:11am CT. The repo is gated (access request / HF login required to read the card and files).
- **Links:** https://huggingface.co/orcarouter/LFM3-1.7B-abliterated · base https://huggingface.co/LiquidAI/LFM3-1.7B · publisher https://www.orcarouter.ai

### SenseNova-Loop-9B-Preview (SenseNova)
@ModelScope2022, Nov 2 12:18am CT. https://x.com/ModelScope2022/status/2117139176168759353
- **What it is:** open-weight multimodal (text + image in, text out) model for long-context and agent work. Looped decoder: layers 4–27 run twice with shared weights, so 56 layer executions from 32 distinct layers (~9B stored params, ~14.6B "inference parameters"). Two-stream manifold-constrained hyper-connections (mHC) in the loop; hybrid attention (3 linear + 1 full per 4-layer group). Trained up to 262,144-token sequences. MTP speculative decoding available; Dspark and Dflash2 in training. Post cites BIRD-Dev 71.38, WorkBuddy Bench 66.89, AIDABench 58.87 (team-reported; leads 6 of 8 tasks in its comparison). Technical report TBD.
- **License:** Apache-2.0.
- **Size and hardware:** BF16 backbone (FP32 mHC routing params), ~38.2 GB repo. Checked environment: Transformers 5.18.0, PyTorch 2.11.0 + CUDA 13.0; card example runs on a single GPU; custom code. Post lists Transformers, LightLLM, SGLang and vLLM deployment paths. Third-party GGUF/NVFP4 builds exist on HF (e.g. AtomicChat/SenseNova-Loop-9B-Preview-GGUF).
- **Release:** card news dated Oct 30 2026; HF repo created Oct 28 2026, updated Nov 2 2026.
- **Links:** https://huggingface.co/sensenova/SenseNova-Loop-9B-Preview · https://modelscope.ai/models/SenseNova/SenseNova-Loop-9B-Preview · https://github.com/OpenSenseNova/SenseNova-Loop · GGUF https://huggingface.co/AtomicChat/SenseNova-Loop-9B-Preview-GGUF

### Qwen3.8-27B-Longbook27-v2 (second post)
@LiLensss, Nov 2 12:31am CT (Chinese). https://x.com/LiLensss/status/2117142551132315673
- **What it is:** Chinese-language write-up of the same model filed in the [Nov 2 scan](2026-11-02-steady-alex-bookmarks.md) (all-GDN linear-attention Qwen3.8-27B variant). Post figures: 262K input in ~55 GB VRAM; layer-wise distillation plus LoRA r32 recovery; NF4 4-bit ~17 GB, fits one 24 GB 3090/4090.
- **Links:** https://huggingface.co/summerAIO/Qwen3.8-27B-Longbook27-v2

### Project Maya v1.1.50 (Peasant Smith / mw00)
@PeasantSmith, Nov 2 11:22am CT. https://x.com/PeasantSmith/status/2117306270352883976
- **What it is:** release of the Maya local inference app (prior: v1.1.47 in Nov 2 scan).
- **v1.1.50 changes (Nov 2 10:43am CT):** Models page (download/load/unload/delete with sizes); Ollama-style model API (`/api/tags`, `/api/ps`, `/api/show`, `/api/chat`, `/api/generate`, `/api/pull`, `/api/delete`, swap-on-request, `keep_alive`); Turbo button (greedy, no thinking, 32K ctx on GLM/MiniMax, expert skipping; up to ~24% faster decode per post); thinking budget setting (default 32768, GLM Maya-XS 8192); new GLM-5.3-Flash Maya-XS quant ~73 GB for 64 GB RAM + 24 GB GPU at 128K context (`glm-maya-xs`); DeepSeek long prompts up to ~19% faster when experts live in RAM; `/tokenize`, `/detokenize`, `response_format` community PRs.
- **Since then:** v1.1.51 (Nov 3 2:31am CT): DeepSeek tensor-parallel expert split follows free VRAM per GPU (~10% more experts in VRAM, up to 10% faster decode; `DS4_TP_SHARES=off` reverts); long prompts ≥~10K up to ~12% faster with most experts in RAM; multi-conversation stop fix; README in Japanese, Simplified Chinese, Brazilian Portuguese.
- **License:** MIT.
- **Links:** https://github.com/mw00/project-maya/releases/tag/v1.1.50 · https://github.com/mw00/project-maya/releases/tag/v1.1.51 · https://github.com/mw00/project-maya

## Keep an eye on this

### Pithos (benmaster82)
@TeksEdge, Nov 1 8:30pm CT. https://x.com/TeksEdge/status/2117081763944026592
- **What it is:** dependency-free C11 inference engine for Liquid AI LFM2 / LFM2-MoE / LFM2.5 / LFM3 GGUF models, single executable: terminal chat, OpenAI-compatible server (prompt reuse across turns), "Pandora" web agent (web search, files, MCP servers), terminal agent (safe or autonomous mode). CPU kernels AVX2/AVX/NEON; optional OpenCL (hot experts in VRAM, rest on CPU, cold experts streamed from disk) and Direct3D 12 (Windows/Xbox). Windows, Linux, macOS on x86-64 and ARM64; Xbox One app in Developer Mode.
- **Reported performance:** LFM2.5-24B-A2B Q4_K_M (13.5 GB) on i5-10500H, 16 GB RAM, GTX 1650 Max-Q 4 GB: Pithos 17.5–21.9 tok/s vs llama.cpp CUDA 11.2–11.3 tok/s (developer-reported, head-to-head dated Oct 24). LFM3-1.7B ~55 tok/s with GPU, ~20 CPU-only; 29.5 tok/s on Xbox One GPU.
- **License:** MIT.
- **Release:** GitHub repo created Oct 27 2026, last push Nov 3 2026; no tagged releases.
- **Links:** https://github.com/benmaster82/Pithos · https://benmaster82.github.io/Pithos/
