# BitNet / bitnet.cpp watch

Source: https://github.com/microsoft/BitNet
Project name on the README: bitnet.cpp. Description on the repo: "Official inference framework for 1-bit LLMs." License: MIT.
Checked 2026-10-12 02:00 UTC (Oct 11 evening CT). GitHub and Hugging Face values below are from that check.

## What it is

bitnet.cpp is Microsoft's inference framework for 1-bit LLMs, in particular BitNet b1.58, whose weights are ternary (about 1.58 bits). The README describes optimized kernels for fast, lossless inference of 1.58-bit models on CPU and GPU, and says NPU support is coming next. The framework is based on llama.cpp, and the README says its kernels build on the lookup-table work in Microsoft's T-MAC.

The official generative checkpoint named in the README is BitNet b1.58 2B4T: 2.4B parameters, trained on 4 trillion tokens, ternary weights, chat-ready. Newer official releases on the same README are two 1-bit embedding models (0.6B and 270M, 2 bits per weight, I2_S kernels) and a news item for VibeASR.cpp, a separate CPU ASR engine that uses BitNet I2_S quantization.

## Current state

No GitHub release objects and no git tags. The README version badge reads 1.0, and the News section dates "bitnet.cpp 1.0 released" to 2024-10-17. `main` last moved on 2026-07-27.

Headline speed and energy figures, as printed in the README overview and attributed there to the CPU technical report (https://arxiv.org/abs/2410.16144):

- ARM CPUs: speedups of 1.37x to 5.07x, energy use down 55.4% to 70.0%.
- x86 CPUs: speedups of 2.37x to 6.17x, energy use down 71.9% to 82.2%.
- A 100B BitNet b1.58 model on a single CPU at 5–7 tokens per second. No 100B checkpoint is in the official Hugging Face set below.
- The 2B model section repeats the top of those ranges: up to 6.17x on x86 and 5.07x on ARM, energy down up to 82.2% (x86) and 70.0% (ARM), versus full-precision models.

Embedding claims in the same README (prefill, 8 threads, versus F16): 1.42x to 2.28x for BitNet-embedding-0.6B, and 1.32x to 1.74x for BitNet-embedding-270M, on x86.

Hardware the repo actually documents:

- CPU. Official 2.4B model: x86 with I2_S and TL2 kernels; ARM with I2_S and TL1. Both embedding models: x86 I2_S only. The supported-models table marks ARM unsupported for the embeddings.
- GPU. A separate CUDA kernel (https://github.com/microsoft/BitNet/blob/main/gpu/README.md), W2A8 (2-bit weights, 8-bit activations), announced in the News section on 2025-05-20. Kernel and end-to-end tables there are measured on an NVIDIA A100 40GB. Kernel speedups versus BF16 on listed shapes run from 1.27x to 3.63x. End-to-end latency versus a similarly sized BF16 model (Gemma-2-2B under vLLM) runs from 2.89x to 3.27x on that GPU.
- NPU: named only as "coming next" in the overview.

Recent commits on `main` (newest first). Activity since March 2026 is the July embedding and VibeASR news cluster; the tip has not moved since 2026-07-27.

- 2026-07-27 `0b341e582afbf9e1011f24744b554c96a3477eb5` — Add VibeASR.cpp release to News (#596). This is the tip of `main`.
- 2026-07-21 `16da220ae2b510caff437d403288882687f44ae5` — Revamp README with structured layout, News section, and Model Releases (#590).
- 2026-07-20 `186365a717ba73e928f4cd1959cfea92ae74d54c` — Update README for BitNet Embedding 0.6B/270M release (#589).
- 2026-07-17 `6f228769736934053af73b6a313a6dfc30ef89bf` — Merge pull request #587, release-bitnet-embedding-0.6b-270m.
- 2026-07-13 `3b04140a54c4e5e14183c607121230b2d6da85dc` — I2_S GGUF conversion for bitnet-b1.58-2B-4T and a T-MAC LUT path refactor.
- 2026-03-09 `eb60fc39cb91d52cc217029a637424247cd79545` — `weights_only=True` on `torch.load` in the GPU inference pipeline (merge #421). Last GPU-path commit before the July cluster.

The README also lists community 1-bit models (1bitLLM, Falcon3, Falcon-E, and others) as demonstration targets. Those are outside the official `microsoft/` set and are not part of the baseline below.

## Access

Checked 2026-10-12 UTC. URLs below returned a page or an API body.

- Repo: https://github.com/microsoft/BitNet
- Releases page (empty on this check): https://github.com/microsoft/BitNet/releases
- GPU kernel notes: https://github.com/microsoft/BitNet/blob/main/gpu/README.md
- CPU kernel notes linked from News (2026-01-15): https://github.com/microsoft/BitNet/blob/main/src/README.md
- Embedding I2_S guide linked from News (2026-07-16): https://github.com/microsoft/BitNet/blob/main/docs/bitnet-embeddings-i2s-guide.md
- Hugging Face collection "BitNet" (lastUpdated 2025-05-01; three model repos and four papers; the July 2026 embedding repos are not in it): https://huggingface.co/collections/microsoft/bitnet
- Online demo linked from the README: https://demo-bitnet-h0h8hcfqeqhrf5gf.canadacentral-01.azurewebsites.net/
- Sibling ASR engine named in the 2026-07-23 news item: https://github.com/microsoft/VibeASR.cpp

Official `microsoft` model repos. The README uses mixed-case ids such as `microsoft/BitNet-b1.58-2B-4T`; the Hub API canonical id is lowercase and the mixed-case URL resolves to the same repo. A search of `author=microsoft` and `search=bitnet` returned these six and no others:

- https://huggingface.co/microsoft/bitnet-b1.58-2B-4T — text generation, MIT, created 2025-04-15 (News date 2025-04-14). Card links arXiv 2504.12285.
- https://huggingface.co/microsoft/bitnet-b1.58-2B-4T-bf16 — BF16 checkpoint the GPU README and the convert script download.
- https://huggingface.co/microsoft/bitnet-b1.58-2B-4T-gguf — GGUF pack the CPU setup example downloads.
- https://huggingface.co/microsoft/bitnet-embedding-0.6b — created 2026-07-15, MIT, README news date 2026-07-20.
- https://huggingface.co/microsoft/bitnet-embedding-270m — created 2026-07-15, MIT, same news item.
- https://huggingface.co/microsoft/VibeVoice-ASR-BitNet — automatic speech recognition, MIT, created 2026-07-24. Linked from the BitNet README news item; not in the BitNet collection.

Papers and reports the README or the official collection link:

- BitNet (original): https://arxiv.org/abs/2310.11453
- The Era of 1-bit LLMs (BitNet b1.58): https://arxiv.org/abs/2402.17764
- Training tips PDF linked from News: https://github.com/microsoft/unilm/blob/master/bitnet/The-Era-of-1-bit-LLMs__Training_Tips_Code_FAQ.pdf
- 1-bit AI Infra, Part 1.1 (CPU inference report behind the speed and energy figures): https://arxiv.org/abs/2410.16144
- BitNet a4.8: https://arxiv.org/abs/2411.04965
- bitnet.cpp system paper: https://arxiv.org/abs/2502.11880
- BitNet b1.58 2B4T technical report: https://arxiv.org/abs/2504.12285
- BitNet v2 (in the HF collection; not in the README news list): https://arxiv.org/abs/2504.18415
- VibeVoice-ASR-BitNet technical report: https://arxiv.org/abs/2607.21075

## Relation to prior notes

This is the same local-compression theme as the Oct 3 extreme-compression cluster (Ternary Bonsai is a ternary Qwen quant with its own runtime; BitNet is Microsoft's 1.58-bit kernels plus their own small official weights) and the Oct 10 Samsung LittleBit note (sub-1-bit research code, non-commercial, no official checkpoints). It also sits with the local-speed items: Oct 5 Strata IQ3_S and Red Hat NVFP4, and the Oct 11 exllamav3 1.6.x + DFlash2 note.

## Feeds

- Commits on `main`: https://github.com/microsoft/BitNet/commits/main
- Releases: https://github.com/microsoft/BitNet/releases
- Tags: https://github.com/microsoft/BitNet/tags
- Hub search that produced the six repos below: `author=microsoft`, `search=bitnet`
- Collection: https://huggingface.co/collections/microsoft/bitnet (still dated 2025-05-01; embeddings and VibeVoice-ASR-BitNet were absent)

**Baseline, 2026-10-12 UTC.**

Release tag: none. GitHub Releases returned an empty list. The tags API returned an empty list. README version badge: 1.0. News line for that version: 2024-10-17.

Latest commit on `main`: `0b341e582afbf9e1011f24744b554c96a3477eb5`, committer date 2026-07-27T05:52:05Z, message "Add VibeASR.cpp release to News (#596)".

Official `microsoft` BitNet Hub repos (API `id`, `createdAt`, `lastModified`, `sha`):

| Hub id | createdAt (UTC) | lastModified (UTC) | sha |
|---|---|---|---|
| microsoft/bitnet-b1.58-2B-4T | 2025-04-15T04:25:13.000Z | 2025-12-17T18:13:05.000Z | 04c3b9ad9361b824064a1f25ea60a8be9599b127 |
| microsoft/bitnet-b1.58-2B-4T-bf16 | 2025-04-15T04:23:53.000Z | 2025-12-17T18:12:29.000Z | 276681394656abdadb8e80e5b2c3db5e5d7fcaff |
| microsoft/bitnet-b1.58-2B-4T-gguf | 2025-04-15T04:25:42.000Z | 2025-12-17T18:12:47.000Z | a1f2f1c765812aa8af3f6eda4a313707064bba15 |
| microsoft/bitnet-embedding-0.6b | 2026-07-15T09:38:59.000Z | 2026-07-17T06:05:53.000Z | 16176d108561b62e3d6f2b558587afe1140b413f |
| microsoft/bitnet-embedding-270m | 2026-07-15T09:25:12.000Z | 2026-07-17T06:05:49.000Z | 5f1c2fd19f37ca653a3d719c8ee6cc1895f4b64f |
| microsoft/VibeVoice-ASR-BitNet | 2026-07-24T06:03:05.000Z | 2026-07-24T06:03:32.000Z | 66e78021ab8f5f06133d1ab421ba4d348bda97c9 |

VibeVoice-ASR-BitNet is an ASR repo that the BitNet README links. The BitNet collection on this check contained only the three `bitnet-b1.58-2B-4T` repos (base, bf16, gguf) plus papers 2504.12285, 2402.17764, 2310.11453, and 2504.18415.
