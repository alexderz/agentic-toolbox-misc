# Steady_Alex bookmarks 2026-11-27 (catch-up)

Catch-up since the last successful run (~4pm CT Nov 24, 2026; `iris/2026-11-24-steady-alex-bookmarks.md`, PR #53). Nine new non-meme bookmarks. None in Memes or Keep an eye on this. Folder split: Moodils 4, Cool tech to try 4, tech updates 1.

Times below are America/Chicago (CST, UTC-6).


## Moodils

### Nemotron-Labs-Image-30B-A3B (NVIDIA)
- Post: https://x.com/ItsmeAjayKV/status/2125574724613034131 (@ItsmeAjayKV, Nov 25, 2026, 6:58am CT)
- Hugging Face: https://huggingface.co/nvidia/Nemotron-Labs-Image-30B-A3B
- Paper: https://arxiv.org/abs/2611.31358 (Nemotron-Labs-VisualCreation: Pixel as Code for Agentic Visual Creation)
- What: open-weight autoregressive text-to-image MoE, the raster-generation component of NVIDIA's Nemotron-Labs-VisualCreation ("Pixel as Code") framework. Initialized from Nemotron 3 Nano. 30B total / 3B active parameters. Bundled Nemotron-Labs-Image-Tokenizer: about 642M-parameter encoder/decoder, 16×16 patches, fixed codebook of 196,560 Leech-lattice vectors; reconstruction on the paper's ~178K-image protocol is 29.57 dB PSNR vs 26.08 dB for Emu3.5 IBQ. Training includes text-to-image and text-and-image-conditioned generation (editing, multi-turn, references). The VisualCreation harness and Nemotron-Labs-VisionCode models are listed as "will be released upon legal clearance."
- Size/hardware: 32 safetensors shards plus a 2.57 GB tokenizer checkpoint (about 133 GB / 124 GiB total). Card example: Linux, Python 3.12, NVIDIA driver compatible with CUDA 13.0, four NVIDIA H100 80GB GPUs; validated stack includes PyTorch 2.11.0+cu130, vLLM 0.21.0, Transformers 5.23.0. Example generates 1024×1024 (patch size 16).
- License: NVIDIA License, non-commercial research and evaluation only (`LICENSE` in the repo; card `license_name`: nvidia-license). Tokenizer modeling files also carry LicenseRef-NvidiaProprietary in NOTICE.
- Publisher: NVIDIA (affiliations on the card also list UNC Chapel Hill, UC Santa Cruz, University of Maryland, and Nanjing University). Weights on the HF repo were last updated 2026-11-25.

### Raon-1 mini (KRAFTON AI) — out of preview
- Post: https://x.com/Krafton_AI/status/2125292128884654433 (@Krafton_AI, Nov 24, 2026, 12:15pm CT)
- Hugging Face: https://huggingface.co/KRAFTON/Raon-1-mini
- Collection: https://huggingface.co/collections/KRAFTON/raon-1-mini (GGUF https://huggingface.co/KRAFTON/Raon-1-mini-gguf, DFlash2 draft https://huggingface.co/KRAFTON/Raon-1-mini-dflash2, NVFP4 https://huggingface.co/KRAFTON/Raon-1-mini-nvfp4, MLX https://huggingface.co/KRAFTON/Raon-1-mini-mlx; preview weights remain at https://huggingface.co/KRAFTON/Raon-1-mini-preview)
- Docs / API: https://raon.krafton.ai/en/docs — base URL https://raon-api.krafton.ai/v1 (OpenAI chat completions and responses; Anthropic messages). Console / signup: https://raon-console.krafton.ai/ ; playground: https://raon-console.krafton.ai/playground . Docs state the hosted model is free for a limited time, with token usage and rate limits still applied. Hosted API and playground use separate terms, not Apache 2.0.
- What: 30B-A4B MoE language model designed and trained from scratch by KRAFTON AI; official release out of preview. 28.8B total / 4.3B active (6 of 128 routed experts plus 1 shared expert per token). 25-layer hybrid: 18 Raon Delta Attention layers with fixed-size state and 7 gated MLA layers (about 8 KiB KV cache per token in BF16). Native context 262,144 tokens. Built-in thinking with six effort levels (`none`, `low`, `medium`, `high`, `xhigh`, `max`). Card scores: AIME 2026 96.7, HMMT Feb 2026 87.1, GPQA Diamond 86.0, MultiChallenge 64.9, BrowseComp Plus 55.9. Inference support listed for Transformers, vLLM, llama.cpp, and MLX.
- Size/hardware: NVFP4 listed as enabling a full 256K context on 20 GiB of VRAM; the card also states a full 256K-token request fits in 24 GB of VRAM with NVFP4 weights and a BF16 KV cache.
- License: Apache 2.0 (weights and in-repo components). Preview was also Apache 2.0.
- Publisher: KRAFTON AI. HF repo created 2026-11-24; post 2026-11-24.

### Inkling-2-Mini-Unbound (nokeepai)
- Post: https://x.com/TeksEdge/status/2125424242045194364 (@TeksEdge, Nov 24, 2026, 9:00pm CT)
- Hugging Face: https://huggingface.co/nokeepai/Inkling-2-Mini-Unbound
- GGUF: https://huggingface.co/nokeepai/Inkling-2-Mini-Unbound-GGUF
- Code: https://github.com/nokeepai/inkling-2-mini-unbound
- What: refusal-reduced fine-tune of Thinking Machines Lab's Inkling 2 Mini (26.4B MoE, Apache 2.0; already filed). Post reports original 0.8% vs modified 85.2% of harmful requests receiving answers in the developer's refusal-behavior evaluation. Those figures match the model card's Unbound v2.1 numbers (useful answers on 263 requests: 83.7% thinking off, 85.2% thinking on; original 0.8%). As of this run the card's current version is v3, released 2026-11-27 (after the post). Same architecture, tokenizer, and chat template as the base model.
- Size/hardware: card recommends GGUF `Q4_K_M` (about 18 GB); Transformers / SGLang / vLLM path reported on one RTX 5090 (32 GB).
- License: Apache 2.0, following the base model.
- Publisher: nokeep / nokeepai. HF repo created 2026-11-21; post 2026-11-24.

### Tencent Hy4 flash local quants (AngelSlim / llama.cpp / Strata)
- Post: https://x.com/TencentHunyuan/status/2125510109417857368 (@TencentHunyuan, Nov 25, 2026, 2:41am CT)
- Hugging Face (base, already filed): https://huggingface.co/tencent/Hy4-flash
- GGUF: https://huggingface.co/AngelSlim/Hy4-flash-GGUF
- Official page: https://hy.tencent.ai/research/hy4-flash
- Code (model): https://github.com/Tencent-Hunyuan/Hy4-flash
- Strata: https://github.com/Niko1221/Strata (branch https://github.com/Niko1221/Strata/tree/hy4-flash-hpc)
- What: Tencent post that Hy4 flash can be run locally using AngelSlim-quantized weights. Post figures: up to 39 tok/s on Spark and 50 tok/s on a 128 GB Mac M5 Max via llama.cpp; up to 58 tok/s on a 24 GB 4090D and 18 tok/s on a 64 GB Mac M4 Pro via Strata, with a `hy4-flash-hpc` branch for larger machines. Base model already filed (220B-total MoE, Tencent Hy license).
- License: Tencent Hy license (base); AngelSlim GGUF follows the base model terms.
- Publisher: Tencent Hy / AngelSlim / Strata (Niko1221). Post 2026-11-25.


## Cool tech to try

### Plato's Key (Stanford Hazy Research)
- Post: https://x.com/Alissonerdx/status/2126024817573011490 (@Alissonerdx, Nov 26, 2026, 12:46pm CT)
- Official page: https://hazyresearch.stanford.edu/blog/2026-11-25-platos-key (Nov 25, 2026)
- What: method for aligning hidden-state "keys" across frozen LLMs with a closed-form rotation and one global scale (orthogonal Procrustes via thin SVD), with no gradient training, fit on fewer than 5,000 facts both models recall. Tested on factual recall across 12 base LLMs from eight families (1.5B–27B), 20 model pairs, 8,800 facts. Reported: median transfer accuracy 41% (self-swap reference 55%; median 73% of self-swap); chained maps A→B→C retain a median 99% of a direct A→C map; a map on 256 principal components retains a median 74% of the full map; a rotated donor key recovers 18% of the recipient's "dark memories" (facts stored but not recalled). Authors: Vivien Cheng, Jerry Liu, Morris Yau, Chris Ré. No official paper or code repository is linked from the blog post.
- Hardware: not a model release; a closed-form linear map.
- Source: Stanford Hazy Research, 2026-11-25.

### OpenGame (nexu-io)
- Post: https://x.com/tuturetom/status/2125885818816561502 (@tuturetom / Tom Huang, Nov 26, 2026, 3:34am CT)
- Repo: https://github.com/nexu-io/opengame (created 2026-11-25)
- Setup: https://github.com/nexu-io/opengame/blob/main/docs/opengame-setup.md
- What: open-source "Super Game Agent" that connects local coding agents to a game-studio pipeline (code, art, 3D, audio, playtest, publish). README lists 22 supported local agents (including DeepSeek, Claude Code, Codex, Gemini CLI, Cursor) and 25 built-in playable templates under `templates/games/`, with publishing paths for WeChat Mini Games, TikTok, Douyin, Telegram, and itch.io. The post states 29 agents, 15+ multimodal models, and 100+ games, and claims the repo was written in 72 hours (~900k lines).
- Hardware: Git, Git LFS, npm, and Node.js 22.18+ (CI pins Node.js 26.11.1). Chrome/Chromium for automated screenshots and play-tests; FFmpeg for trailers. Not a GPU model.
- License: Apache 2.0.
- Publisher: nexu-io / Tom Huang (@tuturetom). Repo created 2026-11-25; post 2026-11-26.

### Cortheon v2 (Ash Hart)
- Post: https://x.com/ashxhart/status/2126076517356609642 (@ashxhart, Nov 26, 2026, 4:11pm CT)
- Repo: https://github.com/ashhart/Cortheon (created 2026-08-24)
- What: open-source runtime for frozen local LLMs: execution-verified parallel consensus (Python / SymPy / Z3 scripts, optional Wave-2 falsification), zero weight updates and no cloud API. Works with TensorFold, Ollama, llama.cpp, vLLM, SGLang, mlx-lm, and LM Studio, plus a proxy in front of an OpenAI-compatible server. Default OS-level sandbox (`sandbox-exec` on macOS, `bwrap` on Linux). Repo README reports official AIME 2025 gains of +16.7 to +30.0 points (pooled 51/90 → 72/90) at about 6–7 calls per problem. The post describes this as open-sourcing Cortheon v2.
- Hardware: local inference backend required; no additional model weights.
- License: MIT.
- Publisher: Ash Hart. Post 2026-11-26.

### Magnitude (inference engine)
- Post: https://x.com/tomgreenwald/status/2125348896805175791 (@tomgreenwald, Nov 24, 2026, 4:00pm CT)
- Site: https://magnitude.dev/ — docs https://docs.magnitude.dev/introduction — hardware https://docs.magnitude.dev/hardware — benchmarks https://magnitude.dev/benchmarks
- Repo: https://github.com/magnitudedev/magnitude (created 2026-06-12)
- What: open-source local inference engine that places sparse-MoE shared layers and hot experts in GPU/unified memory, frequent experts in RAM, and the rest on NVMe SSD, with prefetch and per-chip kernel tuning. Accepts GGUF models from Hugging Face in supported families. Official site example decode speeds (2-bit, 64K context, speculative decoding on): Qwen 3.8 Flash Next 56 tok/s on a Mac mini M5 Pro 48 GB and 54 tok/s on RTX 3090 (24 GB) + 64 GB RAM + PCIe 4.0 SSD; DeepSeek V4.1 Flash 40 tok/s on DGX Spark 128 GB and 17 tok/s on RTX 5090 (32 GB) + 64 GB RAM + PCIe 5.0 SSD.
- Hardware: macOS, Linux, or Windows; Apple Silicon (Metal), NVIDIA Ampere or newer (CUDA), AMD/Intel and other GPUs via Vulkan 1.1+, or CPU only. Desktop app, headless CLI, or Docker. VRAM needs to fit at least the active experts; context can be shortened to the largest power-of-two that fits, not below 32K. On multi-GPU machines a model runs on one GPU.
- License: Apache 2.0.
- Publisher: Magnitude / Tom Greenwald (contributor). Post 2026-11-24.


## tech updates

### Project Maya v1.1.80 (Peasant Smith / mw00)
- Post: https://x.com/PeasantSmith/status/2125513068499091689 (@PeasantSmith, Nov 25, 2026, 2:53am CT)
- Repo: https://github.com/mw00/project-maya
- Releases: v1.1.79 https://github.com/mw00/project-maya/releases/tag/v1.1.79 (2026-11-25 1:31am CT); v1.1.80 https://github.com/mw00/project-maya/releases/tag/v1.1.80 (2026-11-25 2:39am CT)
- Model files: https://huggingface.co/peasantsmith/Inkling-2-Mini-Maya-GGUF (refusal direction: `refusal-directions/Inkling-2-Mini-refusal-direction.gguf`, 9,760 bytes)
- What: the post announces Maya v1.1.80 and lists two Inkling 2 Mini changes. Ablation option (released in v1.1.79): off by default; enable with `--ablation on` in setup, the Models page switch, or `"ablate"` in a request; post reports refusals from 98% to 10% on Maya's test set. Thinking budget (v1.1.80): v1.1.79 defaulted Inkling's thinking cap to 32,768 tokens; v1.1.80 makes the budget optional so Inkling thinks until done unless a budget is set in Settings, config `"thinking_budget"`, or (per the post) per chat / per API request. A previously set budget is kept; re-running setup no longer drops one.
- License: MIT.
- Publisher: mw00 / Peasant Smith. Releases 2026-11-25.
