# Steady_Alex bookmarks 2026-11-24


## Run ~8am CT Nov 24 2026 (1 new bookmark)

### @OrcaCyberHQ Hy4 Flash Abliterated / Uncensored GGUF (quant of an abliterated finetune, not novel)
- Post: https://x.com/OrcaCyberHQ/status/2124053590096630211 (2026-11-21 08:13 UTC; quotes https://x.com/OrcaCyberHQ/status/2123100565559562434)
- Hugging Face: https://huggingface.co/orcarouter/Hy4-flash-abliterated-GGUF (base: abliterated build of tencent/Hy4-flash)
- Press release: https://prtimes.jp/main/html/rd/p/000000144.000138449.html (OrcaRouter's OrcaCyber team, FlashLabs)
- What: GGUF builds of refusal-reduced Hy4-flash; 220B-total MoE (about 63-64B Engram hash-table parameters), about 11-12B active per token; 1M context; mixed-precision stock llama.cpp types (no custom kernels).
- Builds: Mix-128G (3 files, about 138 GB, about 88 GiB resident) and Mix-256G (6 files, about 238 GB, about 178 GiB resident); Engram table read from disk on demand (--lazy-mode auto).
- License: Tencent Hy license (HF repo gated, automatic approval).
- Publisher: OrcaCyber / OrcaRouter, released 2026-11-21.

## Run ~4pm CT Nov 24 2026 (1 new bookmark)

### @UnslothAI Inkling 2 Mini fine-tuning support (training notebook/guide; not novel)
- Post: https://x.com/UnslothAI/status/2125243469094605071 (2026-11-24 15:01 UTC)
- Guide: https://unsloth.ai/docs/models/inkling-2-mini/fine-tuning
- Run-locally guide: https://unsloth.ai/docs/models/inkling-2-mini
- Code: https://github.com/unslothai/unsloth (release https://github.com/unslothai/unsloth/releases/tag/v0.1.924-beta, "Release Inkling finetuning + perf fixes")
- What: Unsloth fine-tuning support for Thinking Machines Lab's Inkling 2 Mini (26.4B MoE, looped transformer); free Colab and Kaggle notebooks (Kaggle on 2x T4).
- Hardware: local training on 22 GB VRAM (QLoRA, about 21.1 GB peak in the guide's example); Unsloth states 1.8-3.1x faster and 50% less VRAM than Hugging Face TRL setups (e.g. 29.4 vs 58.3 GiB on A100 80GB at 2,048 tokens).
- Base model: Inkling 2 Mini (Thinking Machines Lab, Apache 2.0; filed Nov 20-21). Model id in guide: unsloth/Inkling-2-Mini.
- License: Unsloth is open source (see repo).
- Publisher: Unsloth AI, 2026-11-24.

