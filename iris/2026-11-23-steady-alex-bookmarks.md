# @Steady_Alex bookmarks — 2026-11-23

## 12pm CT run

### 2124856757675549143 — step-by-step repo for GPU-to-GPU P2P on RTX 3090s (Ubuntu 26.04)
- Post: https://x.com/kamilskowron/status/2124856757675549143 (@kamilskowron, Nov 23 2026 07:25 CT). Claims 12x lower GPU-to-GPU latency, +46-70% faster data exchange, 0 errors in 1.5 TB of test copies; Ubuntu 26.04 verified on a fresh install. Follow-up to https://x.com/kamilskowron/status/2124580892823711942.
- Repo: https://github.com/Cinderella-Man/how-to-enable-p2p-on-nvidia-gpus (created Nov 23 2026; no license file listed on GitHub). Guide to enabling P2P over PCIe on GeForce cards (tested on two RTX 3090s, two RTX 3080s, and an RTX 2060 + GTX 1650 SUPER with extra steps) using Ubuntu's NVIDIA 615 open driver, CUDA 13.5; replaces NVIDIA's open kernel modules with a patched build.
- Patched modules: https://github.com/Cinderella-Man/geforce-dynbar1-p2p (fork of https://github.com/noon-at-cgn/geforce-dynbar1-p2p; 615.71.09 plus dynamic BAR1 P2P patch series, two fixes for Ubuntu 26.04 / Linux 7.0). Credit in post also to https://github.com/noon-at-cgn.
- Requirements stated: BIOS Above 4G Decoding and Resizable BAR on (BAR1 at least VRAM), Secure Boot off, kernel param iommu=pt, two or more GeForce GPUs. Docs include procedure, Turing notes, troubleshooting, benchmarks (benchmarks dated 2026-11-23), and a security-review doc.

### 2124803137173340245 — OrcaCyber Inkling 2 Mini Uncensored / Abliterated weights
- Post: https://x.com/OrcaCyberHQ/status/2124803137173340245 (@OrcaCyberHQ, Nov 23 2026 03:51 CT). Claims 26.4B parameters, runs locally on 12-16GB RAM, based on Thinking Machines Inkling 2 Mini (Apache 2.0 MoE, looped transformer), 48.2% on DeepSWE v1.1.
- Post links no repo. No HF page under an OrcaCyber org found. Same-name abliterated repos by the orcarouter HF org (created Nov 23 2026 ~23:14 CT Nov 22): https://huggingface.co/orcarouter/Inkling-2-Mini-abliterated-GGUF and https://huggingface.co/orcarouter/Inkling-2-Mini-abliterated-MLX (link to the post not confirmed).
- Base model: Inkling 2 Mini, Thinking Machines Lab, Apache 2.0. Other abliterated variants already on HF: e.g. https://huggingface.co/OpenUncensored/Inkling-2-Mini-Uncensored, https://huggingface.co/mrfakename/Inkling-2-Mini-abliterated. Not novel (abliteration of a filed model).

## 2026-11-23 ~4pm CT run

### 2124899507121139833 — Ling-3.2-air (inclusionAI / Ant Group)
- Post: https://x.com/i/status/2124899507121139833 (Chinese-language announcement of the open-source release)
- Hugging Face: https://huggingface.co/inclusionAI/Ling-3.2-air
- SGLang cookbook: https://docs.sglang.io/cookbook/autoregressive/InclusionAI/Ling-3.2-air
- Type: open-weight native multimodal MoE (image/video input, reasoning, tool calling); 124B total / 5.5B active; FP8 weights, about 129 GB in 13 safetensors shards. License: MIT (per search summary of the HF page).
- Reported (model card): AutomationBench-AA 15.7% to 61%; Terminal-Bench 4.0 0% to 27%; Artificial Analysis Intelligence Index v5.0.1 score 23.

### 2124890020263727264 — SSD expert streaming for DeepSeek V4.1 (post, author not confirmed)
- Post: https://x.com/i/status/2124890020263727264 ("ship this tomorrow morning"; benchmarks on Mac M2/M4 Pro, RTX 3090/5090, DGX Spark; up to 3x streamed decode gain; full SSD expert streaming for DeepSeek V4.1). No repo linked in the post text.
- Related public projects (not confirmed as the post's source): https://github.com/davidtai/mlx-stream (DeepSeek-V4.1-Flash plugin for mlx-serve, experts streamed from SSD, EXL3 3.0 bpw); https://github.com/antirez/ds4 (docs/DGX_SPARK.md); https://dwarfstar.sh/docs/deepseek-v4-1-flash/ (V4.1 Flash Q2 341 GiB, SSD streaming on 128GB Mac/Spark/Strix Halo).


## Run ~7:46pm CT Nov 23 2026 (2 new bookmarks)

### @MOVNTDQ deslop-please (linter for code structure)
- Post: https://x.com/MOVNTDQ/status/2124947434078155043 (2026-11-23 19:25 UTC; quotes https://x.com/poteto/status/2121673563489140863)
- Repo: https://github.com/deterministic-machines/deslop-please (Rust, MIT, created 2026-11-22; crates.io: deslop-please, `cargo install deslop-please`)
- What: opinionated linter following "A Philosophy of Software Design" (deep modules, narrow interfaces); reports e.g. field-leak across modules; supports an allow-file. Post claims 23 issues found/fixed in bbtree and fewer tokens per task.
- Hardware: CLI, no GPU. Not novel.

### @kamilskowron RTX 20 / GTX 16 BAR hack (256 MB window opened to full VRAM)
- Post: https://x.com/kamilskowron/status/2124906227826073754 (2026-11-23 16:41 UTC; quotes https://x.com/kamilskowron/status/2124892466394374340, a GTX 1650 SUPER + RTX 2060 multi-GPU post)
- Post says: every RTX 20 / GTX 16 card exposes a 256 MB CPU/peer-visible window into VRAM; author claims a hack that exposes all of it. No repo or license linked in the post. Related prior filed item: his GeForce P2P how-to (2124856757675549143). Not novel.


## Run ~11:54pm CT Nov 23 2026 (1 new bookmark)

### MemT-1.0-Pro (MemTensor x NVIDIA), memory-native model
- Post: https://x.com/i/status/2124623963087126562 (2026-11-22 22:00 UTC; launch of MemT-1.0-Pro with @NVIDIAAIDev, compared to MemT-1.0-Flash)
- Hugging Face: https://huggingface.co/MemTensor/MemT-1.0-Pro (family: MemT-1.0-Nano https://huggingface.co/MemTensor/MemT-1.0-Nano)
- Code: https://github.com/MemTensor/MemT-1.0 ; paper: https://arxiv.org/abs/2610.26825 ; press release: https://www.prnewswire.com/news-releases/memtensor-releases-and-open-sources-memt-1-0-pro-a-554b-memory-native-model-302948905.html
- What: open-weight model with a native memory block alongside attention (dynamic local memory plus trainable hyper memory); persistent state constant in size, about 66x less storage than full-context KV cache at 128K history (per model card). Pro: backbone NVIDIA-Nemotron-3-Ultra-550B-A55B, 554B total / 59B active, 4.23B trainable memory parameters, 13M dynamic memory state. Family: Nano (Qwen3.6-35B-A3B, 36B/3B), Flash (DeepSeek-V4-Flash, 288B/17B), Pro.
- License: OpenMDW-1.1 (Pro, following the Nemotron backbone); inference code portions Apache-2.0.
- Size/hardware: 226 safetensors shards (about 5 GB each, bf16); card loads with Transformers, trust_remote_code=True, bf16, device_map=auto, sdpa attention.
- Publisher: MemTensor with NVIDIA; distributed training with Megatron-Core and Megatron Bridge.
