# @Steady_Alex bookmark scan, Oct 10 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Sat Oct 10, 2026 ~9:12am CT. Baseline: [Oct 9 delta](2026-10-09-steady-alex-bookmarks.md) (56 total) on main.

## Summary

- **Total bookmarks:** 62 (one page, `result_count` 62, no `next_token`, page size 100).
- **New vs Oct 9 baseline:** 6 ids. All 56 baseline ids still present.
- **Memes skipped:** 1 new — 2108663800102609008 (@toxiccowboy02, Memes folder). Memes folder now holds that plus the Oct 5 skip (2107021822155985254).
- **Folders:** no new folders. Cool tech to try now has 7; Moodils now has 9; Keep an eye on this now has 2; Cyber and folder set unchanged (Memes, Moodils, Cool tech to try, Keep an eye on this, Cyber).

## Cool tech to try

### Living Weights in TensorFold — local models that update their own weights while serving

@ashxhart, posted Oct 9 10:27am CT. Continues the TensorFold cluster (Oct 3 catalog). "Living Weights" / Sliding Weights (`tensorfold serve --slide`) lets a served Nemotron 3.5 Lightning checkpoint learn facts during use: each kept fact becomes a change to the model's output-projection weights, written into the checkpoint's safetensors shards, so any TensorFold server started from that folder answers with it after a restart or when the folder is moved to another machine. Facts come from `POST /v1/slide/learn` (or an omp `/learn` extension); a fact is kept only if related questions it was never trained on still answer correctly. Ships in TensorFold 1.0.3+ (1.0.4 adds a safety refuse when `--slide` would rewrite a Hugging Face cache hard-link). Learning is Mac/Metal-only for now (NVIDIA refuses `--slide`, though CUDA can serve a folder that learned on a Mac); a fact takes ~2–4 minutes. Recall tests are small, and writes into the model folder are irreversible.
https://x.com/ashxhart/status/2108580126094963038

**Access:**

- Engine / releases: https://github.com/ashhart/TensorFold · v1.0.3+ release notes describe Sliding Weights / Living Weights
- Install: Homebrew `brew upgrade tensorfold`, or release archives from the GitHub releases page
- Example HF pull targets used by TensorFold (not Living Weights itself): e.g. `TensorFold/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-MLX-4bit` via `tensorfold pull` — org https://huggingface.co/TensorFold
- Not a new base model; no separate Living-Weights HF card. Apache-2.0 engine; model weights keep their own licenses.

### Helix Foundry — local-first company ontology on HelixDB + DuckDB

@georgecurtiss (HelixDB), posted Oct 8 8:49pm CT. Open-source local-first data workspace: connect databases, Stripe, WorkOS, PostHog, files, and APIs; it suggests a shared ontology and lets you ask questions with SQL citations. Graph/object store is HelixDB (S3-backed); analytics run in isolated DuckDB over immutable Parquet snapshots. No accounts — runs on your computer; local AI default (`qwen3:4b` via Ollama) or Claude/OpenAI. Docker Compose setup; first run several GB. Security model is single-user localhost-only on port 3001 (anyone who can reach the app controls every workspace). Early (no tagged releases called out in secondary coverage); Apache 2.0.
https://x.com/georgecurtiss/status/2108374327980933516

**Access:**

- Source: https://github.com/HelixDB/helix-foundry (Apache 2.0)
- HelixDB (underlying DB): https://github.com/HelixDB/helix-db · docs https://docs.helix-db.com
- DuckDB: https://duckdb.org
- Not a model, so no Hugging Face entry for Foundry itself. Local AI path uses Ollama's `qwen3:4b` (or bring Claude/OpenAI keys).

## Moodils

### Mirai S & Bonsai 2 — incremental serve patches (more VRAM positions, faster deep agent turns)

@CaryPalmerr, posted Oct 9 8:19pm CT. Follow-up on the Bonsai / Mirai consumer-GPU cluster (Oct 3 catalog). Incremental patch updates for Mirai S and Bonsai 2 serving stacks: more KV/positions kept in VRAM when the card allows, and faster agent turns especially at depth / longer context. Same ternary / Mirai weights; changes are in the serve/patch repos, not new weight edits. Continues the 12 GB RTX 4070 story (262k context, tiered q8 KV, agent/tool-call fixes).
https://x.com/CaryPalmerr/status/2108729077339238717

**Access:**

- Mirai S patch: https://github.com/professorpalmer/mirai-s-ada
- Bonsai 2 patch: https://github.com/professorpalmer/bonsai-ada-surgery
- Mirai S weights (official experimental): https://huggingface.co/trymirai/Qwen3.8-27B-S-experimental
- Bonsai 2 weights (official): https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf · base https://huggingface.co/Qwen/Qwen3.8-27B
- PrismML runtime context: https://github.com/PrismML-Eng/Bonsai-demo · llama.cpp fork https://github.com/PrismML-Eng/llama.cpp

### Qwen-Image-2.1-Turbo — 8-step open image gen/edit checkpoint

@Alibaba_Qwen, posted Oct 9 8:24am CT. Accelerated checkpoint of Qwen-Image-2.1 (same 7B visual generation architecture): text-to-image and natural-language edits in **8 denoising steps**, CFG=1, sampling schedule saved in the checkpoint and loaded by Diffusers' `QwenImage21Pipeline`. Open weights; Pro and Turbo hosted APIs live on Alibaba Cloud Model Studio. Continues the Qwen-Image-2.1 thread from the Oct 3 catalog (GGUF / VRAM-split posts).
https://x.com/Alibaba_Qwen/status/2108549075218120949

**Access:**

- Hugging Face (official): https://huggingface.co/Qwen/Qwen-Image-2.1-Turbo
- Base model: https://huggingface.co/Qwen/Qwen-Image-2.1
- ModelScope: https://modelscope.cn/models/Qwen/Qwen-Image-2.1-Turbo
- Turbo API (Model Studio): https://modelstudio.console.alibabacloud.com/ap-southeast-1/model/market/detail/qwen-image-2.1-turbo?serviceSite=international&ref=list
- Pro API: https://modelstudio.console.alibabacloud.com/ap-southeast-1/model/market/detail/qwen-image-2.1-pro?serviceSite=international&ref=list
- Docs: https://www.alibabacloud.com/help/en/model-studio/qwen-image-2-1-turbo
- Community GGUF: https://huggingface.co/unsloth/Qwen-Image-2.1-Turbo-GGUF
- Needs recent Diffusers with pipeline-configured sampling sigmas; Qwen Research License on weights.

## Keep an eye on this

### Samsung LittleBit — sub-1-bit LLM compression via latent factorization (research code)

@thesupermannx, posted Oct 8 2:35am CT. Samsung Research open-sourced LittleBit (NeurIPS 2025) and LittleBit-2 (ICML 2026): extreme compression by low-rank latent factorization + binarized factors + multi-scale compensation, targeting ~0.1–1.0 bits per weight (paper: Llama2-13B under ~1 GB). QAT method (not one-shot post-training); repo ships training/eval code, not production inference kernels or ready-to-run checkpoints. License **CC BY-NC 4.0** (non-commercial). Speedup claims are kernel-level, not end-to-end product numbers. Foldered under Keep an eye on this.
https://x.com/thesupermannx/status/2108098865073410484

**Access:**

- Official code: https://github.com/SamsungLabs/LittleBit (CC BY-NC 4.0)
- Paper (HF Papers): https://huggingface.co/papers/2506.13771
- Samsung Research page: https://research.samsung.com/research-papers/LittleBit-Ultra-Low-Bit-Quantization-via-Latent-Factorization
- No official pretrained LittleBit checkpoints on HF as of this scan; eval scripts can load a Hub id.

## Skipped (Memes)

- 2108663800102609008 — @toxiccowboy02, Oct 9 4:00pm CT. Short video meme in Memes folder. Ignored per watch rules.
