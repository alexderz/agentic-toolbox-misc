# @Steady_Alex bookmark scan, Oct 23 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Fri Oct 23, 2026 ~9:20am CT. Baseline: [Oct 22 delta](2026-10-22-steady-alex-bookmarks.md) (96 total, newest id 2112981571716415961).

## Summary

- **New vs baseline:** 5 ids (newest 25 bookmarks read; the 6th onward were already filed).
- **Total:** 101 if no baseline ids were removed (full list not re-paged this run).
- **Memes skipped:** none new.
- **Folders:** no new folders (Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). All 5 new posts are in Moodils.

## Moodils

### Kaitchup Qwen3.8-27B SLQ — mixed-precision quantized Qwen3.8-27B (three checkpoints)

@bnjmn_marie (Benjamin Marie), posted Oct 21 3:18pm CT. Post text: "statistically-lossless" Qwen3.8-27B, three models 23.7–30.5 GB (up to 57% smaller than BF16), 98–99% measured EAR vs 97.71% for native FP8; vLLM + Humming; Apache 2.0; GGUF versions "coming next week"; based on SLQ from ISTA DASLab.
https://x.com/bnjmn_marie/status/2113002020567453798

- **What it is:** Qwen/Qwen3.8-27B compressed with a customized SLQ (Statistically-Lossless Quantization) search that picks precision per projection (including selected attention heads) from GPTQ INT2–INT8, AutoRound and ISTA-DASLab GSQ 3-bit candidates plus original BF16 weights. Activations stay BF16; original MTP weights kept in BF16. Packed for the Humming kernels in vLLM.
- **EAR (Expected Acceptance Rate):** overlap of next-token probabilities with BF16, renormalized over the BF16 reference's top-10 tokens. Card table: BF16 100% (55.563 GB); official FP8 97.71% (30.867 GB); Unsloth UD-Q4_K_XL GGUF 97.44% (17.559 GB); SLQ EAR98 98.00%; EAR98.5 98.50%; EAR99 99.00%.
- **Checkpoints and weight-file sizes (HF):**
  - `kaitchup/Qwen3.8-27B-SLQ-EAR98`: 23.73 GB
  - `kaitchup/Qwen3.8-27B-SLQ-EAR98.5`: 25.61 GB
  - `kaitchup/Qwen3.8-27B-SLQ-EAR99`: 30.52 GB (card: file size, not total serving memory)
- **Runtime:** vLLM with Humming. GGUF versions announced as coming.
- **License:** Apache-2.0 (all three repos).
- **Release:** The Kaitchup (HF org `kaitchup`). Repos created Oct 21 3:00–3:05pm CT; collection updated Oct 21 3:05pm CT. Method: SLQ paper arXiv 2605.02404, IST-DASLab/SLQ repo.

**Links:**

- HF collection: https://huggingface.co/collections/kaitchup/qwen38-27b-slq
- HF (EAR98): https://huggingface.co/kaitchup/Qwen3.8-27B-SLQ-EAR98
- HF (EAR98.5): https://huggingface.co/kaitchup/Qwen3.8-27B-SLQ-EAR98.5
- HF (EAR99): https://huggingface.co/kaitchup/Qwen3.8-27B-SLQ-EAR99
- SLQ paper: https://arxiv.org/abs/2605.02404
- SLQ code: https://github.com/IST-DASLab/SLQ
- Base model: https://huggingface.co/Qwen/Qwen3.8-27B

### Recursive Flint 40B-A2.5B on a single RTX 3060 (community run report)

@DogukanUrker (Doğukan), posted Oct 21 7:10pm CT, quoting @RichardSocher's Flint launch post. Post text: Flint on one RTX 3060, 12 GB VRAM + 16 GB RAM; 256K context; ~46 tok/s decode, ~675 tok/s prefill; llama.cpp support not merged, run on llama.cpp PR #30928 cherry-picked onto master; 14 of 49 layers are full attention, so 256K context uses 3.8 GB of q8 KV cache. Config: `llama-server -m flint-preview-UD-Q3_K_XL.gguf -ngl 99 --n-cpu-moe 33 -c 262144 -fa on --jinja -np 1 --cache-ram 0 --cache-type-k q8_0 --cache-type-v q8_0 -b 2048 -ub 1024 --temp 1.0 --top-p 0.95 --top-k 20 --min-p 0.0 --repeat-penalty 1.0`.
https://x.com/DogukanUrker/status/2113060329038970892

- **Model:** Recursive Flint (filed Oct 22, see [Oct 22 note](2026-10-22-steady-alex-bookmarks.md)). Apache-2.0.
- **Quant used:** Unsloth UD-Q3_K_XL. Current file in `unsloth/flint-GGUF` is `flint-UD-Q3_K_XL.gguf`, 18.49 GB (post names it `flint-preview-UD-Q3_K_XL.gguf`). Repo created Oct 19 10:26pm CT, Apache-2.0.
- **llama.cpp PR #30928:** "models: Add Flint model (FlintForCausalLM)" by alexey-rsi, opened Oct 21 9:48am CT, closed without merge Oct 21 4:26pm CT.
- **Launch post quoted:** @RichardSocher, Oct 21 11:29am CT (Flint, Recursive's first model; 125+ tok/s on MacBook Pro, 150+ on RTX Spark; free on OpenCode and Pi).

**Links:**

- HF (Unsloth GGUF): https://huggingface.co/unsloth/flint-GGUF
- HF (BF16): https://huggingface.co/RecursiveSI/flint
- llama.cpp PR: https://github.com/ggml-org/llama.cpp/pull/30928
- Launch post: https://x.com/RichardSocher/status/2112944385415426249

### Hugging Face Carbon-X — open 14B DNA + text language model

@lvwerra (Leandro von Werra), posted Oct 22 9:37am CT. Post text: took Qwen3.5 14B and mid- and post-trained it to beat other open models and match frontier models on DNA understanding; trained on natural language and DNA so you can "chat to your DNA"; full recipe released.
https://x.com/lvwerra/status/2113278666507485349

- **What it is (HF card):** 14.8B-parameter decoder-only model trained jointly on DNA sequences and English. Raw DNA goes in a chat message; it predicts benign vs pathogenic variants, finds regulatory regions, classifies sequences by organism group, predicts next bases, and explains its reasoning. Single decoder, no separate DNA encoder; hybrid tokenizer (Qwen3 BPE plus 5,515 DNA tokens, DNA as non-overlapping 6-mers).
- **Specs:** 40 layers, hidden 5120, GQA (40 query / 8 KV heads), SwiGLU, RMSNorm + QK-norm. Context 40,960 tokens. Post-trained and evaluated with thinking disabled. Training: 302B tokens of mid-training (DNA, biology text, English, instructions), then SFT and RL with verifiable rewards.
- **Base model:** HF card metadata lists `Qwen/Qwen3-14B` (post says Qwen3.5 14B).
- **Card benchmarks:** 66.7% average across five DNA benchmarks (thinking off), 27 points above Qwen3-14B; GPT-6.1 Sol 67.5% at about 1,800× the per-problem cost (Carbon-X cost from H200 throughput at $5/hour).
- **Size and hardware:** BF16 safetensors 29.64 GB; card says weights fit on a single 80 GB GPU in bfloat16; serves with vLLM on one GPU. Needs Transformers v5+ and `trust_remote_code=True` for the tokenizer.
- **License:** Apache-2.0 (model); code repo huggingface/carbon Apache-2.0.
- **Release:** Hugging Face Bio (HF org `HuggingFaceBio`). Model repo created Oct 21 5:21am CT, last modified Oct 22 4:55am CT. Blog is an HF Space.

**Links:**

- HF (model): https://huggingface.co/HuggingFaceBio/Carbon-X
- Blog: https://huggingface.co/spaces/HuggingFaceBio/Carbon-X-Release
- Code: https://github.com/huggingface/carbon
- Org: https://huggingface.co/HuggingFaceBio

### Qwen3.8-Flash-Next quant comparison: GSQ-RCO-IQ3_S vs Unsloth UD-Q4_K_XL (video)

@unbug, posted Oct 22 11:02am CT. Post text: GSQ-RCO-IQ3_S (left) decodes 1.3× faster; both runs finished in 32 minutes; UD Q4_K_XL (right) "clearly wins on detail". Two videos attached.
https://x.com/unbug/status/2113300045277925814

- **Quants compared (HF):**
  - `ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF`, IQ3_S: two shards, 54.82 + 28.80 GB (~83.6 GB). Repo created Sep 7, Apache-2.0. Same repo also has IQ2_XS, IQ3_XXS, Q2_0 and a BF16 mmproj (0.91 GB).
  - `unsloth/Qwen3.8-Flash-Next-GGUF`, UD-Q4_K_XL: four shards, ~111.3 GB total.

**Links:**

- HF (ISTA-DASLab GSQ-RCO GGUF): https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF
- HF (Unsloth GGUF): https://huggingface.co/unsloth/Qwen3.8-Flash-Next-GGUF

### tqLLM 1.2 — inference engine running Qwen3.8 Flash-Next on one RTX 3090

@coffeecup2020 (David Y. Tan), posted Oct 22 8:44am CT. Post text: Qwen3.8 Flash-Next on one RTX 3090, tqLLM 1.2 vs Strata 0.2.2: 1.63× faster decode at 128K context (77 vs 47 tok/s), 3× faster first token on chats, 77 tok/s after a 128K-token prompt; Metal version "coming soon"; runs on 32 GB RAM with an RTX 3090.
https://x.com/coffeecup2020/status/2113265219283660816

- **What it is:** open-source local inference engine (tqLLM) with a Qwen3.8 Flash-Next (125B MoE) setup that runs the ISTA-DASLab GSQ-RCO IQ3_S GGUF with an expert cache in system RAM.
- **Releases (tqllm.com/releases), all Oct 22 2026:**
  - 1.2.0: Flash-Next on one RTX 3090; vs Strata 0.2.2 on the same GGUF and card, 77.1 vs 47.2 tok/s decode after a 128K prompt, 1.34× after 64K, first token 0.32–0.41 s vs 1.07–1.29 s on short chats.
  - 1.2.1: runs from the public HF files alone (51 GB packed-expert file no longer needed; experts arranged in memory at start-up, ~50 s).
  - 1.2.2: GB10 / DGX Spark support from the HF files; engine sizes expert cache on device at start-up.
  - 1.2.3: full speed from HF files; RTX 3090 cold start, chats 96–103 tok/s, 32K-prompt first token 14.6 s; per-layer token embedding (28.8 GB) now read once at start-up (~6 s).
- **Distribution:** Docker images `ytan2000/tqllm:<version>` and `ghcr.io/turbo-tan/tqllm:<version>` (x86-64 and arm64). HF setup repo `YTan2000/Qwen3.8-Flash-Next-tqLLM` (created Oct 22 10:07am CT, Apache-2.0, base ISTA-DASLab GSQ-RCO GGUF).
- **License:** Apache-2.0 (site and GitHub `turbo-tan/tqllm`, repo created Oct 2, 40 stars at pull time). Site: model weights keep their own licenses.
- **Hardware stated:** RTX 3090 24 GB with 32 GB system RAM (post); GB10 / DGX Spark (1.2.2).

**Links:**

- Releases: https://tqllm.com/releases
- Site: https://tqllm.com/
- GitHub: https://github.com/turbo-tan/tqllm
- HF setup: https://huggingface.co/YTan2000/Qwen3.8-Flash-Next-tqLLM
- Strata (compared): https://github.com/Niko1221/Strata
