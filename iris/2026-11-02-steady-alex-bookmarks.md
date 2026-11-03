# @Steady_Alex bookmark scan, Nov 2 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Mon Nov 2, 2026 ~9:20am CT. Baseline: [Nov 1 scan](2026-11-01-steady-alex-bookmarks.md) (139 total).

## Summary

- **New vs baseline:** 6 ids (all above the Nov 1 set on page 1).
- **Total:** 145 if no baseline ids were removed.
- **Memes skipped:** none.
- **Folders:** no new folders (still Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). Moodils +3, Keep an eye on this +1, Cool tech to try +2.

## Moodils

### Qwopus3.8-27B-Coder-Flash (Jackrong / Kyle Hessling)
@KyleHessling1, Nov 1 4:01pm CT. https://x.com/KyleHessling1/status/2117014256361394321
- **What it is:** coding/agentic fine-tune of Qwen3.8-27B (via unsloth/Qwen3.8-27B), image-text-to-text with vision projector. ~200K training examples: ~20K agent/tool-use trajectories distilled mainly from Qwen3.8-Flash-Max; code generation from Qwen3.8-Flash-Max, Qwen3.8-Max and DeepSeek-V4-Flash teachers; reasoning/instruction data from NVIDIA Nemotron sets. Post says it was RL'd with a new reward approach.
- **License:** Apache-2.0.
- **Size:** GGUF Q4_K_M 16.81 GB, Q5_K_M 19.54 GB, Q6_K 22.43 GB, Q8_0 29.05 GB, mmproj-F32 1.84 GB. Runs on llama.cpp.
- **Release:** HF repo created Oct 27 2026 (CT), last modified Nov 1.
- **Links:** https://huggingface.co/Jackrong/Qwopus3.8-27B-Coder-Flash-GGUF · base https://huggingface.co/Qwen/Qwen3.8-27B

### TensorFold Living Weights: Qwen ports on CUDA (Ash Hart)
@ashxhart, Oct 31 10:15pm CT. https://x.com/ashxhart/status/2116730699139240071
- **What it is:** update to TensorFold's Living Weights (in-serving weight learning via `--slide`, see [Oct 10 note](2026-10-10-steady-alex-bookmarks.md)). Experimental CUDA learning ports now include Qwen3.8 Flash Next and dense Qwen3.8-27B; per the post, GPU validation for the 27B port is pending. Nemotron 3.5 Lightning learning remains supported on Metal and CUDA.
- **Related release notes:** TensorFold v1.2.1 (Nov 1 2026) adds `DELETE /v1/slide/facts` (removes facts as one reversible change), Nemotron Omni learning on CUDA, and lists a known issue that Qwen3.8-27B learning on CUDA has a gradient 1.6–1.8x too large at a prompt's last row (learning gates stop bad lessons; serving without lessons unchanged). TensorFold Mac app 1.0.0 (Nov 2 2026) bundles engine 1.2.0.
- **License:** Apache-2.0 (engine repo).
- **Links:** https://github.com/ashhart/TensorFold · https://github.com/ashhart/TensorFold/releases/tag/v1.2.1 · https://github.com/ashhart/TensorFold/releases/tag/app-v1.0.0

### Project Maya v1.1.47 (Peasant Smith / mw00)
@PeasantSmith, Nov 1 11:12am CT. https://x.com/PeasantSmith/status/2116941386729615549
- **What it is:** release of the Maya local inference app (prior note: v1.1.42 on Nov 1).
- **Changes (release notes):** DeepSeek V4.1 Maya-XS v2 quant, KLD 0.251 vs 0.284 (about 12% closer to original) and about 20% faster decode, 117 GB; existing users update via setup without re-downloading n-gram tables. Unsloth's DeepSeek quants now share Maya's Q6_K n-gram tables (Q8 download 508 → 467 GB). Monitor UI changes. `/models/load`, `/models/unload`, `/models/sse` endpoints on by default (`"model_management": false` disables). `--engine maya` server flag.
- **License:** MIT.
- **Release:** v1.1.47 published Nov 1 2026 10:50am CT.
- **Links:** https://github.com/mw00/project-maya/releases/tag/v1.1.47 · https://github.com/mw00/project-maya

## Keep an eye on this

### Mistral-Large-4-1T-A52B GGUF (OrcaRouter)
@OrcaRouter, Oct 31 11:52pm CT. https://x.com/OrcaRouter/status/2116755292092604794
- **What it is:** mixed-precision imatrix GGUF builds of mistralai/Mistral-Large-4-1T-A52B (1T-param MoE, 128 routed experts top-4 plus one shared, 52B active, MLA attention, DeepSeek-style sparse attention, 1M context). Per-expert-group precision chosen from measured KL divergence.
- **Builds (card):** Mix-256G 232.9 GB, 1.72 bpw experts, KLD 0.0975, top-1 agreement 91.6%, PPL +8.7%; Mix-512G 492.2 GB, 3.72 bpw experts, KLD 0.0129, top-1 96.9%, PPL +0.75%. Card claims 20% / 13% lower KLD than Unsloth UD-IQ1_S / UD-Q3_K_XL at the same size. Scored against a Q8_0 GGUF of the official FP8 checkpoint.
- **Hardware (card):** Mix-256G for a 256 GB Mac, 256 GB CPU box, or 2× H200; Mix-512G for a 512 GB Mac/server or 4× H200. llama.cpp.
- **License:** other, Mistral ecosystem open-weight license (LICENSE in repo).
- **Release:** HF repo created Oct 31 2026 8:20pm CT. Repo ~726 GB total (6 + 12 shards plus imatrix).
- **Links:** https://huggingface.co/orcarouter/Mistral-Large-4-1T-A52B-GGUF · base https://huggingface.co/mistralai/Mistral-Large-4-1T-A52B · publisher https://www.orcarouter.ai

## Cool tech to try

### Qwen3.8-27B-Longbook27-v2
@dextune, Nov 1 10:00am CT. https://x.com/dextune/status/2116923227070939174
- **What it is:** 27B long-form text fine-tune (books, papers, long reports), English and Japanese. Custom architecture `qwen3_5_gdn24`: per the post, the base model's 16 full-attention layers are replaced with Gated DeltaNet, so all 64 layers are linear-attention. Shipped as remote code; `trust_remote_code=True` required. ChatML-style template with `enable_thinking`.
- **License:** Apache-2.0.
- **Size and hardware (card):** BF16 safetensors ~54 GB (A100 80 GB / H100 class); 4-bit NF4 ~17 GB (24 GB GPUs). Whole model must be on GPU (CPU offload unsupported). Optional `flash-linear-attention` and `causal-conv1d` kernels.
- **Release:** HF repo created Oct 22 2026. Third-party GGUF parser-tech/Qwen3.8-27B-Longbook27-v2-GGUF (IQ4_XS with Q8 gates, 15.31 GB) created Nov 2 2026.
- **Links:** https://huggingface.co/summerAIO/Qwen3.8-27B-Longbook27-v2 · GGUF https://huggingface.co/parser-tech/Qwen3.8-27B-Longbook27-v2-GGUF

### FlashAlign 1.1.1 (Aevonix)
@Kurcide, Oct 31 11:59pm CT. https://x.com/Kurcide/status/2116756976243998734
- **What it is:** release of FlashAlign (per-request abliteration profiles on served weights; prior note Nov 1). New DeepSeek V4.1 Flash profile based on @u1tra_instinct's abliteration.
- **Changes:** v1.1.0 (Oct 31 10:00pm CT) replaces the DeepSeek starter with a native Keys profile (26 WO-B matrices and 26 scale tensors per authorized request), pinned native vLLM backend for the official DeepSeek V4.1 Flash 1017 FP8 checkpoint, 1.09 GB profile payload from the public release with SHA-256 check. v1.1.1 (Oct 31 10:59pm CT) adds TensorFold 1.2.0 support for that profile; TensorFold path needs the pinned LibertAIDAI EXL3 3.5-bpw checkpoint, Linux x86_64, four SM120 GPUs, strength 1.0; JSON-schema/guided output unsupported. SGLang and llama.cpp do not implement this operator.
- **Profile source:** https://huggingface.co/drowzeys/keys-DeepSeek-V4.1-Flash-1017-Abliterated (MIT notice and responsible-use agreement apply to the profile).
- **License:** FlashAlign software AGPL-3.0-only, commercial license option.
- **Links:** https://github.com/Aevonix/FlashAlign/releases/tag/v1.1.1 · https://github.com/Aevonix/FlashAlign/releases/tag/v1.1.0 · https://github.com/Aevonix/FlashAlign/blob/main/docs/native-tensorfold.md
