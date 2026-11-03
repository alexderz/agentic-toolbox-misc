# @Steady_Alex bookmark scan, Oct 18 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Sun Oct 18, 2026 ~9:20am CT. Baseline: [Oct 15 delta](2026-10-15-steady-alex-bookmarks.md) (81 total); Oct 16 and Oct 17 runs found nothing new.

## Summary

- **New vs baseline:** 5 ids (newest 10 bookmarks read; the 6th through 10th were already filed).
- **Total:** 86 if no baseline ids were removed (full list not re-paged this run).
- **Memes skipped:** none new (Memes folder still holds 2108663800102609008 and 2107021822155985254).
- **Folders:** no new folders. Moodils 16 → 20 (+4: Hy-Memory, Qwen3.8 FP4-Local, Lucebox DS4.1 1017, GLM-5.3-Flash on RTX 3090); Keep an eye on this 7 → 8 (+1: DeepSeek V4.1 Flash 1017 API sighting); Cool tech to try 14; Cyber 2; Memes 2.

## Moodils

### Hy-Memory-30B-A3B — Tencent Hunyuan long-term-memory writer model

@TeksEdge (David Hendrickson), posted Oct 16 11:30am CT. Tencent Hunyuan model whose job is the write path of an agent memory system: it reads new conversation / agent activity, decides what to keep, writes and updates entries in a persistent memory bank. HF card: drop-in replacement for the general-purpose LLM inside Mem0, MemOS and Hy-Memory (Chat, Working, Coding scenarios); also evaluated on held-out EverMemOS. Training: Memory On-Policy Distillation, then Attributed Memory RL. Card Table 1 (cross-harness average, fixed 20% subsamples): Hy-Memory-30B-A3B 55.49, Claude Opus 5 54.62, DeepSeek V4.1 Flash 53.64, Hy3 51.63, Qwen3.6-35B-A3B 50.37, Qwen3-30B-A3B 44.37. Per-harness for Hy-Memory-30B-A3B: Mem0 54.02, Hy-Memory 60.55, MemOS 50.51, EverMemOS 56.89.
https://x.com/TeksEdge/status/2111132564710990044

- **Size:** 30.06B total parameters (BF16 safetensors, ~60.1 GB repo); ~3B active per token (MoE). Official FP8 repo ~30.6 GB.
- **Community quants (sizes per the post):** Q4_K_M ~17 GB, Q5_K_M ~20 GB, Q6_K ~23 GB, EXL3 4.08bpw ~15 GB. MLX 4-bit / 8-bit and AWQ builds also on HF.
- **Serving:** vLLM (card tested v0.31.0) with OpenAI-compatible API, `--served-model-name hy-memory`; post also lists SGLang. Card example uses `reasoning_effort: "no_think"`.
- **License:** Apache-2.0 (HF card). GitHub repo license field reads NOASSERTION.
- **Release:** HF repo created Oct 15 2026 4:52am CT; FP8 repo Oct 16. GitHub releases v1.0.0 (Oct 16), v1.0.2 (Oct 16), v1.0.4 (Oct 18).

**Links:**

- HF (weights): https://huggingface.co/tencent/Hy-Memory-30B-A3B
- HF FP8: https://huggingface.co/tencent/Hy-Memory-30B-A3B-FP8
- GitHub (framework + eval): https://github.com/Tencent-Hunyuan/Hy-Memory
- Tech report (arXiv 2610.22196, "Hy-Memory-30B-A3B: Attributed Reinforcement Learning for Long-Term Memory Writing"): https://arxiv.org/abs/2610.22196
- Community GGUF examples: https://huggingface.co/rapatsky/Hy-Memory-30B-A3B-GGUF · https://huggingface.co/vinnipukh/Hy-Memory-30B-A3B-GGUF
- Community EXL3 4.08bpw: https://huggingface.co/jyohukuchan/Hy-Memory-30B-A3B-exl3-4.08bpw

### NVIDIA Qwen3.8-Flash-Next-FP4-Local — local FP4 build, 1M-context run report

@jtdavies (John T Davies), posted Oct 16 11:22am CT. Post image is the HF card for `nvidia/Qwen3.8-Flash-Next-FP4-Local`. Post text: "MAJOR upgrade", faster, larger KV pool, up to 1M context; tested 400k context at 56 tok/s (YaRN x2), planning 1M; mentions @MiaAI_lab's TensorFold recipe as 20% faster.
https://x.com/jtdavies/status/2111130634672644152

- **What it is:** NVIDIA Model Optimizer quantization (quantization-aware distillation, "FP4 QAD 1.0", nvidia-modelopt v0.47.0) of Alibaba's Qwen3.8-Flash-Next. Base: hybrid attention (Gated DeltaNet + Qwen Sparse Attention), MoE, vision encoder; 125B total / 6B active, plus 51B n-gram embedding and 4B MTP. Input text, image, video.
- **Context:** 262K native, extensible to 1,000,000 tokens (card).
- **Size / hardware (card):** ~96 GiB on disk (repo ~102 GB). Validated with vLLM on NVIDIA RTX PRO 6000 Blackwell (single GPU, n-gram embedding table offload, 850K tokens FP8 KV cache) and NVIDIA DGX Spark (1M tokens FP8 KV cache with offload). Blackwell only; Linux.
- **Runtime:** card says the NVFP4 scale factors use a new compression format not yet in upstream vLLM; requires community containers `eugr/spark-vllm-b12x:latest` (DGX Spark) or `ghcr.io/local-inference-lab/vllm:release-10152026` (RTX PRO 6000).
- **License:** NVIDIA Open Model Agreement; base model under Qwen Community License 1.0.
- **Release:** card release date 10/05/2026; HF repo created Oct 8; series of README updates Oct 15 2026 (last 2:45pm CT), the day before the post.

**Links:**

- HF (this build): https://huggingface.co/nvidia/Qwen3.8-Flash-Next-FP4-Local
- HF base: https://huggingface.co/Qwen/Qwen3.8-Flash-Next
- Earlier NVIDIA NVFP4 build: https://huggingface.co/nvidia/Qwen3.8-Flash-Next-NVFP4
- NVIDIA Model Optimizer: https://github.com/NVIDIA/Model-Optimizer
- RTX PRO 6000 container: https://github.com/local-inference-lab/blackwell-llm-docker/pkgs/container/vllm
- DGX Spark container: https://hub.docker.com/r/eugr/spark-vllm-b12x/tags?name=latest
- NVIDIA Open Model Agreement: https://www.nvidia.com/en-us/agreements/enterprise-software/nvidia-open-model-agreement/

### Lucebox DeepSeek-V4.1-Flash-1017 ROCMFP GGUF — day-0 quants for AMD Strix/Gorgon Halo

@davideciffa (mrciffa, Lucebox), posted Oct 17 1:23pm CT. Day-0 Lucebox quantizations of DeepSeek-V4.1-Flash-1017; post says usable on 128 GB Strix/Gorgon Halo machines with ~6 GB offloading, and Lucebox units get the optimized quants from Oct 18.
https://x.com/davideciffa/status/2111523493502488784

- **What it is:** GGUF builds for the Lucebox DS4.1 engine (AMD Radeon AI PRO R9700 + Ryzen AI Max), routed experts in Lucebox ROCMFP block formats (2.5-bit fp2s / 3.5-bit fp3), attention/shared experts/head in Q8_0. Needs the Lucebox engine build (`luce_server`); card says readers that ignore the fp2s mirror bit produce garbage.
- **Files (card):** ROCMFP2S 383 GB (158 GiB experts; KL 0.265, top-1 78.6%); ROCMFP2S-MIX10 388 GB (KL 0.244); ROCMFP23S 405 GB (179 GiB experts; KL 0.195, top-1 81.5%); `-IM1017` variants calibrated on 1017 weights. DSpark drafter GGUFs 7.4 GiB (MXFP4-Q8) and 4.6 GiB (Q2K-Q4K); vision mmproj BF16 0.90 GiB. Teacher (fp4 checkpoint) 510 GB, ppl 8.56.
- **Hardware (card):** ROCMFP2S-IM1017 is what the 128 GB Lucebox installs (hot experts on R9700, rest on Ryzen AI Max and SSD); MIX10 for 192 GB boards (`--profile ds41-gorgon`); ROCMFP23S for two-box setups.
- **License:** MIT (same as base). Lucebox engine repo Apache-2.0.
- **Release:** HF repo created Oct 17 2026 9:52am CT, based on `deepseek-ai/DeepSeek-V4.1-Flash-1017` revision `1bae0e10`.

**Links:**

- HF (this build): https://huggingface.co/Lucebox/DeepSeek-V4.1-Flash-1017-ROCMFP-GGUF
- Lucebox engine: https://github.com/Luce-Org/lucebox (`server/docs/DS41.md`)
- Lucebox site: https://www.lucebox.com
- Base model: https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017

### GLM-5.3-Flash on a single RTX 3090 — aj9o9 hand-mixed GGUF

@ItsmeAjayKV (AJ), posted Oct 16 5:42am CT (Japanese). Reports running GLM-5.3-Flash locally on RTX 3090 + 64 GB RAM + NVMe SSD with quant AJ-IQ2_XXS: decode 20–25 tok/s, prefill 800–1000 tok/s, context 256k; credits "Project-Maya". Quotes his own Oct 16 post noting OpenCode offers DeepSeek-v4.1-flash and GLM-5.3-Flash free at 200k context.
https://x.com/ItsmeAjayKV/status/2111045102529593718

- **What it is:** community GGUF of Z.ai GLM-5.3-Flash (320.6B total / 17.3B active; 45 layers, 34 Kimi Delta Attention + 11 MLA; card lists 1,048,576 context in GGUF metadata). MTP block pruned (313.33B in files).
- **Files (card):** AJ-IQ2_XXS 87.35 GB (2.23 bpw, 2 shards; "24 GB card with 64 GB system RAM"); AJ-IQ3_XXS 112.40 GB (2.80 bpw, 3 shards; 128 GB unified memory or 96 GB card with small spill). KV cost per card at f16: 32K 0.44 GB, 131K 1.55 GB, 300K 3.45 GB.
- **Card benchmarks:** AJ-IQ2_XXS resident on a 96 GB card tg256 69.89 tok/s; single RTX 3090 + 64 GB DDR5 with `-ncmoe 40` pp2048 36.69, tg128 11.55 tok/s (the post's 20–25 tok/s figure is the poster's own setup).
- **Runtime:** needs llama.cpp PR #27752 (unmerged; commit "llama : skip foreign-sequence cells when building the glm5next k-pools" or later).
- **License:** MIT (card; base GLM-5.3-Flash).
- **Release:** HF repo created Aug 26 2026, last modified Sep 1 2026. Prior notes on GLM-5.3-Flash: Oct 9, Oct 12, Oct 15.

**Links:**

- HF (this build): https://huggingface.co/aj9o9/GLM-5.3-Flash-GGUF
- HF base: https://huggingface.co/zai-org/GLM-5.3-Flash
- llama.cpp PR #27752: https://github.com/ggml-org/llama.cpp/pull/27752

## Keep an eye on this

### DeepSeek-V4.1-Flash-1017 — API sighting, now officially released

@aitrackerbot (AI Tracker Bot, run by @SSHCodes), posted Oct 16 10:18pm CT. Reported `deepseek-v4.1-flash-1017` briefly appearing in DeepSeek's API model list at 9:59pm ET Oct 16, then being rejected. As of this run it is officially released.
https://x.com/aitrackerbot/status/2111295736411300047

- **What it is:** minor update to DeepSeek-V4.1-Flash; DeepSeek says better reasoning, coding, agentic and visual benchmarks with shorter outputs and faster task completion. Card numbers (1017 vs V4.1-Flash): HLE w/o tools 42.6 vs 36.8; Terminal-Bench 4.0 42.3 vs 31.2; DeepSWE v1.1 77.0 vs 74.2; ProgramBench 29.1 vs 20.3; Apex Bench v1.1 72.1 vs 64.6.
- **Release:** DeepSeek news "DeepSeek-V4.1-Flash-1017 Release" dated 2026/10/17; live on web, app and API. HF repo created Oct 16 2026 9:40pm CT.
- **API:** model name `deepseek-flash` now serves DeepSeek-V4.1-Flash-1017 (legacy `deepseek-v4-flash` / `deepseek-v4-flash-vision-exp` also routed to it). 1M context, max output 384K, thinking and non-thinking modes, JSON output, tool calls, Responses API, Anthropic API, vision. Pricing per 1M tokens (peak / off-peak): input cache hit $0.006 / $0.003, cache miss $0.30 / $0.15, output $1.20 / $0.60. Concurrency limit 2500. DeepSeek says calling method and pricing unchanged.
- **Weights:** checkpoint ~510 GB on HF (FP8 / INT8 / BF16 mix). No Jinja chat template; Python reference encoder in repo plus `deepseek-recipe` Rust/Python toolkit. Recommended sampling temperature 1.0, top_p 1.0, max_tokens ≥ 256K.
- **License:** MIT (repo and weights).

**Links:**

- HF (weights): https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017
- Tech report (V4.1): https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash/blob/main/DeepSeek_V41_Tech_Report.pdf
- Release note: https://api-docs.deepseek.com/news/news261017
- API pricing / models: https://api-docs.deepseek.com/quick_start/pricing
- API platform / signup / keys: https://platform.deepseek.com
- Chat: https://chat.deepseek.com/
- deepseek-recipe: https://github.com/deepseek-ai/deepseek-recipe
- Community quants already up include `unsloth/DeepSeek-V4.1-Flash-1017-GGUF`, `LibertAIDAI/DeepSeek-V4.1-Flash-1017-NVFP4`, and the Lucebox build above.

## Skipped (Memes)

- None new. Memes folder unchanged: 2108663800102609008, 2107021822155985254.
