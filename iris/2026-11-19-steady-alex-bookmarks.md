# Steady_Alex bookmarks, 2026-11-19

## ~12am CT run
New bookmark: 2123202426609999937 (post by @coldniko, 2026-11-18 23:51Z). All other newest-10 bookmarks already filed.

### Strata v0.2.16 (own engine code, no llama.cpp kernels) (post 2123202426609999937)
- **What it is:** release of Strata, a one-click local-AI app/terminal with its own inference engine and OpenAI/Anthropic-compatible localhost API. v0.2.16 engines (0.1.62) run on Strata's own code for NVIDIA, AMD, Intel Arc and Mac, with no ggml or llama.cpp matrix kernels; own picture reader (file 53,864,888 to 807,976 bytes on NVIDIA). Release notes report identical tokens to 0.2.15 on their 10 test prompts on most tested GPUs; fixes Mac M1-M4 UD-Q4_K_XL wrong results in 0.2.15; folder layout moved to engine/, app/, terminal/, docs/, tools/. Strata earlier filed in iris/ (Edge0/Strata models).
- **Links:** post https://x.com/coldniko/status/2123202426609999937 · GitHub https://github.com/Niko1221/Strata · release https://github.com/Niko1221/Strata/releases/tag/v0.2.16
- **License:** MIT (GitHub).
- **Size and hardware:** Windows, Linux, Mac, DGX Spark; NVIDIA, AMD, Intel Arc, Apple Silicon.
- **Release:** Niko1221/Strata v0.2.16, published 2026-11-18 21:57Z (previous v0.2.15 on 2026-11-16).

## ~8pm CT run
New bookmarks: 2123517538697125897 (@QuixiAI, 2026-11-19 20:43Z) and 2123520167611428988 (@superalesha, 2026-11-19 20:53Z). All other newest-15 bookmarks already filed.

### QuixiInfer: Rust single-GPU inference engine for DeepSeek-v4.1-Flash-1017 (post 2123517538697125897)
- **What it is:** inference engine by Eric Hartford (@QuixiAI), implemented from scratch in Rust, inspired by DeepInfer and Strata; dynamic CPU and NVMe offloading. Post figures: DeepSeek-v4.1-Flash-1017 on a single GPU at 256k context, ~25-30 tok/s, up to 3 concurrent requests on an RTX 5090. Post asks for testers on other GPUs (3090, 4090, AMD).
- **Links:** post https://x.com/QuixiAI/status/2123517538697125897 · GitHub https://github.com/QuixiAI/QuixiInfer
- **License:** MIT (GitHub).
- **Size and hardware:** RTX 5090 in post benchmark; model weights and RAM/NVMe requirements not stated in the post.
- **Release:** QuixiAI; GitHub repo created 2026-10-28, last push 2026-11-19 23:11Z.

### maya-hy4f: Tencent Hy4-flash on 1-4x RTX 3090 with runtime abliteration (post 2123520167611428988)
- **What it is:** Alexey Fateev (@superalesha) engine "maya-hy4f" built on Project Maya, running Tencent Hy4-flash (220B, 512 experts per layer, 16 active) with 262,144 context, vision, Q8 KV cache and MTP speculative decoding. Post figures (RTX 3090s at 300W, CUDA 12.8, Linux): 1x 3090 IQ2+NVMe (45 GiB RAM) 54-68 tok/s decode, 1,184-1,199 prefill; 1x 3090 Q3_K in RAM 37-54 decode; 2x 3090 70-123 decode; 4x 3090 Q3_K in VRAM 176-251 decode, 2,947 prefill. Single-card path keeps hot experts in VRAM, runs cold experts on CPU AVX2, streams the 59 GiB Engram table from NVMe (O_DIRECT, Linux AIO). Also includes runtime abliteration: a 4 MB refusal-direction file projected out at run time without changing weights; post results: AdvBench 64 + JailbreakBench 82 (thinking off) 139/146 -> 32/146 refused; AdvBench 24 (thinking on) 22/24 -> 3/24; harmless 64 1/64 -> 0/64; top-token match to stock 85.7% on long text, median KL 0.014. Post cites AngelSlim for Q3_K being near-lossless; IQ2 trunk (51 GB) 74-76% top-token match.
- **Links:** post https://x.com/superalesha/status/2123520167611428988 · docs + build http://github.com/alesha-pro/project-maya/blob/hy4-flash/docs/HY4-FLASH.md · repo https://github.com/alesha-pro/project-maya · Hugging Face (weights + vector) https://huggingface.co/alesha-pro/Hy4-flash-Uncensored-GGUF · base model https://huggingface.co/tencent/Hy4-flash
- **License:** Project Maya repo MIT (GitHub); HF repo license "other" (Tencent Hy License inherited from base; LICENSE file in repo).
- **Size and hardware:** HF repo total storage ~201.7 GB; files: IQ2_XXS (2 shards), Q3_K (2 shards), refusal-directions.bin, mmproj bf16, 1/2/4-GPU configs, abliteration scripts. Hardware per post: 1x RTX 3090 + 64 GB RAM (IQ2 + NVMe) up to 4x RTX 3090.
- **Release:** alesha-pro; HF repo created 2026-11-19 12:11Z, last modified 21:08Z; GitHub repo created 2026-10-10, last push 2026-11-19 21:09Z.
