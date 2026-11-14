# @Steady_Alex bookmarks, Nov 14, 2026

## 12pm CT run (Nov 14, 2026)

Five bookmarks new since the Nov 13 notes (all unfiled folder, 0 memes).

### Edge0-145B and Edge0-120B (Edge0 / AutoArk)
- **What it is:** open-weight latent sparse MoE agent models for a single consumer NVIDIA GPU: 145B total, 48 layers, 512 experts, 10 active per token, 256K context, trained natively at 4 bits. Runs through the Edge0 engine (edge0-strata, edge0-infer, OpenAI- and Anthropic-compatible local server, Edge0 Chat desktop app). HF card figures: terminal-bench 2.1 score 86.5; RTX 5090 D 24 GB Q3_K 121.2 tok/s agent decode, 3554.9 tok/s 16K prefill; RTX 4090 24 GB Q3_K 91.7 tok/s agent decode; 16 GiB VRAM + 20 GiB RAM Q3_K 44.9 tok/s agent decode; Apple M2 Ultra Q3_K 57.0 tok/s.
- **Links:** post https://x.com/TeksEdge/status/2121324972266406008 · HF https://huggingface.co/Edge0/Edge0-145B-q3k · https://huggingface.co/Edge0/Edge0-145B-NVFP4 · code https://github.com/Edge0-AI/Edge0 (release v0.2.0) · blog https://edge0.ai/blog/introducing-edge0-145b-frontier-ai-capabilities-on-your-own-computer
- **License:** Hugging Face license tag "other" (license text on the HF repo); the Edge0-145B-q3k HF repo was not checked beyond that tag.
- **Size and hardware:** NVFP4 build with residency used 23.25 GiB VRAM + 38.27 GiB host RAM on an RTX 5090 D; Q3_K tested with a 16 GiB VRAM + 20 GiB host RAM budget (stated as test limits). Release v0.2.0: Windows x64/Arm64 and Linux with CUDA 13 on NVIDIA compute capability 7.5+, 16 GiB GPU memory, 20 GiB system memory; macOS 26+ Apple Silicon (Metal, Q3_K only). Repo storage on HF about 105 GB for the q3k repo.
- **Release:** Edge0 v0.2.0 with the 145B and 120B models; HF q3k repo created Nov 11, 2026.

### MiniMax-H3-Image quantizations (post by @mingzi206, Chinese-language)
- **What it is:** post on community quantizations of MiniMaxAI/MiniMax-H3-Image, a 33.1B-parameter open-weight unified text-to-image and image-editing model (dense single-stream DiT, 50 layers, Qwen3-VL text encoder from MiniMax-H3, 6-step distilled, no CFG, native ~16 MP up to 4096x4096 and 6272x2688, up to 16 reference images). Post claims 27 quantizations and 110k+ downloads within days; Q4 10.78 GB, Q2_K 6.4 GB, Unsloth FP8 18.8 GB; ComfyUI GGUF and Mac MLX weights.
- **Links:** post https://x.com/mingzi206/status/2121204595842277694 · HF official https://huggingface.co/MiniMaxAI/MiniMax-H3-Image · prompt expander https://huggingface.co/MiniMaxAI/MiniMax-H3-Image-PE · quantizations list https://huggingface.co/models?other=base_model:quantized:MiniMaxAI/MiniMax-H3-Image · API/app: https://platform.minimax.io (global), https://hailuoai.video
- **License:** MiniMax-H3-Image Community License Agreement (separate written authorization under its Section IV via an application form).
- **Size and hardware:** original DiT BF16 68.65 GB (transformer 66.28 GB, VAE 2.34 GB); text encoder 66.7 GB loaded from MiniMaxAI/MiniMax-H3; PE model NVFP4 17.9 GB. Serving via SGLang, vLLM-Omni, diffusers, LightX2V, ComfyUI.
- **Release:** official HF repo created Nov 3, 2026 by MiniMax.

### FlashTopK (Tencent Hunyuan x University of Edinburgh), post by @NFT_Chen
- **What it is:** fused exact top-k selection kernel for learned sparse attention training and inference, part of HyScale (paper "HyScale: Scaling Long-Context Training for Learned Sparse Attention"). Paper: FlashTopK finds each query's exact top-k without a score table, plus selection replay in recomputation; GLM-5.1 training on 1M-token sequences 2.07x faster than Megatron-LM on 512 H20 GPUs; CSA layers of DeepSeek-V4-Flash 2.01x and QSA layers of Qwen3.8-Flash-Next 1.57x at 1M tokens on 32 H800 GPUs. Post cites Indexer Top-K time 5.32 s to 1.62 s and support for GLM-5 series and Hy4-preview.
- **Links:** post https://x.com/NFT_Chen/status/2121346806668050677 · code https://github.com/Tencent-Hunyuan/FlashTopK · paper https://arxiv.org/abs/2610.32057 · site http://flashtopk.select
- **License:** not shown on the GitHub page fetched (GitHub API license field empty).
- **Size and hardware:** GPU kernels; paper results on H20 and H800 clusters.
- **Release:** repo and paper from Tencent Hy and University of Edinburgh (post Nov 13, 2026).

### Project Maya v1.1.62 (mw00 / PeasantSmith)
- **What it is:** release of the Maya local inference app. New (Linux, experimental): AMD Strix Halo / Gorgon Halo APUs paired with an NVIDIA GPU sharing one model (ROCm + CUDA side by side, NVIDIA card can be in a USB4/PCIe dock). Tested on Gorgon Halo (Radeon 8065S) + Tesla V100 32 GB, ROCm 7.14, CUDA 12.4. A/B (APU alone vs both): GLM-5.3-Flash prefill 32K 293 to 901 tok/s (+208%), decode 26.6 to 32.1 (+21%); DeepSeek-V4.1-Flash decode 36.8 to 43.5 (+18%), prefill 32K with `--mixed-gpus split` 615 to 1,062 (+73%). Also GLM decode after a prefill on AMD APUs faster (+5% to +40%). `--mixed-gpus off` disables.
- **Links:** post https://x.com/PeasantSmith/status/2121371735157264831 · release https://github.com/mw00/project-maya/releases/tag/v1.1.62 · repo https://github.com/mw00/project-maya
- **License / cost:** free to use (per release notes); sponsorship at https://github.com/sponsors/mw00. License file not checked.
- **Release:** v1.1.62 published Nov 13, 2026 4:33pm CST.

### T3 Tots announcement (post by @Deepusleepy, Oct 26, 2026)
- **What it is:** original launch post for T3 Tots, a Grok Bot companion for T3 Code (does the routine parts and surfaces only items needing attention; works across multiple computers). Name credit to @poteto. Video attached (38 s). Release v1.4.34 was filed in the Nov 13 note.
- **Links:** post https://x.com/Deepusleepy/status/2114928745647895003 · repo https://github.com/Deepusleepy/t3-tots
- **License:** MIT (per Nov 13 note).
