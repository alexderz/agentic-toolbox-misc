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
