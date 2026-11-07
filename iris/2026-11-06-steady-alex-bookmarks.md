# @Steady_Alex bookmark scan, Nov 6 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Fri Nov 6, 2026 ~7:51pm CT. Baseline: [Nov 5 scan](2026-11-05-steady-alex-bookmarks.md) (highest snowflake then `2118432349352595528` Hyperkernel; filed through tqLLM `2118365037567820178`). Highest snowflake after this run: `2118822925445050435` (Arete-27B).

## Summary

- **New vs baseline:** 5 bookmark ids (4 Moodils + 1 Keep an eye on this), filed as 4 items (Jake's two llamAmpere posts deduped).
- **Memes skipped:** none checked (Memes folder ignored per rules).
- **Folders:** unchanged (Moodils, Cool tech to try, tech updates, Keep an eye on this, Memes, Cyber). Moodils +4 ids; Keep an eye on this +1; Cool tech / tech updates / Cyber unchanged.

## Keep an eye on this

### Mirage (Cactus Compute)
@cactuscompute, Nov 6 11:44am CT. https://x.com/cactuscompute/status/2118761482343313844
- **What it is:** 51.3M-parameter visual model (blog: 7.8M encoder + 40.8M decoder) that, in a single local pass, returns scene description, open-vocabulary object detection with boxes/attributes, OCR with boxes/scores, instance segmentation masks, spatial relations/events, structured form extraction/decisions, and an optional short reasoning trace. Descriptions in English, German, French, Spanish, Italian, Dutch, and Polish. Runs in the same Cactus binaries as Needle and Whistle. Blog latency on Samsung Galaxy S26: 74 ms NPU / 107 ms CPU end-to-end. Install: `pip install -U cactus-compute` then `cactus.Mirage().describe(...)`. Blog also reports a small composition experiment: feeding Mirage's structured record to text-only Qwen3-0.6B on 256 VQAv2 questions scored 31.3/100 (vs 9.3 without Mirage; 22.2 with another image's record).
- **License:** Apache-2.0 (GitHub `cactus-compute/cactus` LICENSE; PyPI `cactus-compute` 4.0.1; HF card `license: apache-2.0`).
- **Size and hardware:** HF deployment file `mirage.cact` 21,611,043 bytes (~20.6 MB; blog cites ~22 MB / 21.6 MB at 2-bit Cactus Quants). Also ships `mirage.safetensors` 216,370,504 bytes (~206.3 MB). Targets phones, wearables, robots, and other consumer devices; Python package downloads engine + weights on first use; native `cactus_load` / `cactus_describe` for apps.
- **Release:** Blog dated November 6, 2026 (authors: Henry Ndubuaku, Karen Mosoyan, Jakub Mroz, Parkirat Sandhu, Justin H. Lee, Satyajit Kumar, Roman Shemet). HF repo `Cactus-Compute/mirage` created Nov 5 2026 1:01pm CT (2026-11-05T19:01:53Z); lastModified Nov 6 2026 ~12:51pm CT. PyPI `cactus-compute` 4.0.1 uploaded Nov 5 2026 5:30pm CT (2026-11-05T23:30:18Z).
- **Links:** https://cactuscompute.com/blog/mirage · https://huggingface.co/Cactus-Compute/mirage · https://github.com/cactus-compute/cactus · https://pypi.org/project/cactus-compute/

## Moodils (look once)

### llamAmpere v0.6.3 + Swift 1.5 Qwen3.8 Flash-Next ATX-AI3
@JakeKAllDay, Nov 6 12:56pm CT announce + 12:59pm CT link post. https://x.com/JakeKAllDay/status/2118779699253907763 · https://x.com/JakeKAllDay/status/2118780239228928223
Announce claims: 120+ TPS and >3K tok/s prompt processing on a single RTX 3090 + 64 GB RAM; 12% faster than Strata; 27% lower error than v3.1 Unsloth 3 XXS; 50% lower error than Strata's original 3XS file.
- **What it is:** llama.cpp fork tuned for NVIDIA Ampere (esp. RTX 3090 / 3090 Ti), with Qwen3.8 / Flash-Next support, expert split across GPU+RAM, mb-MTP drafting, and an OpenAI-compatible `llama-server`. v0.6.3 ships a new Flash-Next weight file in JakeATX's AI+ format (`qwen3.8-flash-next-Swift1.5-ATX-AI3`), which the card says will not load on older llamAmpere or stock llama.cpp. Card size/quality vs IQ3_XXS: 80.11 GB download, KLD 0.086541 vs 0.1744/0.1753 historical; needs companion MTP drafter `mtp-Swift-Qwen3.8-Flash-Next-GSQ-RCO-Q2S-B.gguf` (1.52 GB). Card speed table (RTX 3090, 100K prompt, 5,120 tokens written, temp 1.0): writing ~121–125 tok/s across coding/agentic/RAG vs Strata v0.2.11 ~108–115 tok/s (product comparison, different quality/draft settings).
- **License:** Engine MIT (GitHub). Weights: Swift Open License v1.0 on top of Qwen Community License 1.0 (same as base `ukisai/Swift1.5-Qwen3.8-Flash-Next`; HF tag `license:other`).
- **Size and hardware:** Model download 80.11 GB (two GGUF parts 40.36 + 39.76 GB) + 1.52 GB drafter. Card: one 24 GB RTX 30-series, or a 12 GB card with 64 GB system RAM; launcher keeps ≥5 GiB RAM free; build needs CUDA 12+ toolkit, CMake, sm_86.
- **Release:** GitHub tag `v0.6.3` published Nov 6 2026 9:02am CT (2026-11-06T15:02:01Z). HF model created Nov 6 2026 1:29am CT (2026-11-06T07:29:06Z). Author: JakeATX / @JakeKAllDay.
- **Links:** https://github.com/JakeATX/llamAmpere · https://github.com/JakeATX/llamAmpere/releases/tag/v0.6.3 · https://huggingface.co/jakeatx/qwen3.8-flash-next-Swift1.5-ATX-AI3 · drafter https://huggingface.co/jakeatx/Swift-1.5-Qwen3.8-Flash-Next-MTP-Drafter-GGUF

### OrcaCyber Ripple-65B Abliterated (GGUF + MLX)
@OrcaRouter, Nov 5 10:38pm CT. https://x.com/OrcaRouter/status/2118563684511531458
Post: "OrcaCyber Ripple 65B Abliterated / Uncensored is available in GGUF and MLX formats. Run a 65B model locally with less than 24GB of memory."
- **What it is:** Abliterated (refusal-removed) builds of already-filed `ricursiveAI/Ripple-65B-Preview` (65B dense, agentic coding, up to 1M context claimed). Publisher-measured harmful-prompt refusal average 11.8% vs 95.5% on the original (AdvBench/JailbreakBench/StrongREJECT/HarmBench/MaliciousInstruct/SimpleSafetyTests/ForbiddenQuestions); capability benches within run-to-run noise on MMLU / MMLU-Pro / GSM8K / CMMLU. GGUF mixed-precision builds in stock llama.cpp types (needs PR #31692 / master); MLX builds ship bundled `ricursive.py` and need `mlx-lm>=0.32.2` with `--trust-remote-code`.
- **License:** Apache-2.0 (inherited from Ripple-65B-Preview; both HF cards).
- **Size and hardware (publisher tables):** GGUF — Mix-2.5bit 20.0 GB, Mix-3bit 24.0 GB, Mix-4bit 32.0 GB, Mix-8bit 63.9 GB, BF16 129.6 GB. MLX — 24GB Mac 18.8 GB, 32GB 22.5 GB, 48GB 31.0 GB, 64GB 42.0 GB (peak memory notes on card; MLX files measured on H200s, Apple Silicon speed not stated). KV cache ~2.4 GB at 32K / ~8.9 GB at 128K F16/BF16 on top of weights.
- **Release:** HF GGUF created Nov 5 2026 9:59pm CT (2026-11-06T03:59:56Z); MLX created Nov 5 2026 9:57pm CT (2026-11-06T03:57:38Z). Uploader org: OrcaRouter / Continuum AI (`orcarouter`).
- **Links:** https://huggingface.co/orcarouter/Ripple-65B-abliterated-GGUF · https://huggingface.co/orcarouter/Ripple-65B-abliterated-MLX · base https://huggingface.co/ricursiveAI/Ripple-65B-Preview · https://www.orcarouter.ai/

### Arete-27B (Nous Research)
@NousResearch, Nov 6 3:48pm CT. https://x.com/NousResearch/status/2118822925445050435
- **What it is:** Supervised fine-tune of Alibaba `Qwen/Qwen3.8-27B` (27B dense VLM LM weights; vision encoder frozen during SFT; MTP head disabled in training) aimed at shifting framing/factual recall on seven value categories (freedom of expression, state ideology, state vs free market, education, data privacy/surveillance, democracy, environmental policy). SFT only: ~52.8M tokens, ~50k samples, 64k context, 2 epochs / 1,202 steps, AdamW, teacher Inkling, text-only data. Publisher eval (803-prompt Propaganda_Eval, Grok 4.7 judge): fact mean 2.32 → 2.98 / 5; any-propaganda 22% → 0.9% (thinking off, temp 0); Hermes Bench 65.77% → 65.60%; Terminal-Bench-2.1 67% → 70% (same harness; no credit claimed for the gain). Training dataset and eval published alongside weights.
- **License:** Apache-2.0 (HF card).
- **Size and hardware:** 27B params; HF Transformers safetensors in 18 shards (`model-00001-of-00018.safetensors` …). Same class of local hardware as Qwen3.8-27B (base is a 27B dense hybrid-attention VLM with native 262K context). No GGUF in the primary repo at pull time.
- **Release:** Blog "November 2026"; HF repo created Nov 6 2026 1:31pm CT (2026-11-06T19:31:28Z); lastModified Nov 6 2026 ~3:04pm CT. Developer: Nous Research. Evaluated checkpoint: step 1,202.
- **Links:** https://nousresearch.com/arete · https://huggingface.co/NousResearch/Arete-27B · eval https://huggingface.co/datasets/NousResearch/Propaganda_Eval · training data https://huggingface.co/datasets/NousResearch/arete-data-pairs · base https://huggingface.co/Qwen/Qwen3.8-27B

---

## Update: Nov 6 2026 ~11:58pm CT run

Pulled Fri Nov 6, 2026 ~11:57pm CT. New vs baseline: 1 bookmark id (Cool tech to try). Folders unchanged (6). Highest snowflake still `2118822925445050435`.

## Cool tech to try

### "Can LLMs redesign themselves as they train?" (doubleAI)
@_doubleAI_, Nov 6 9:52am CT, 6-post thread. https://x.com/_doubleAI_/status/2118733156069032292
- **What it is:** Research blog post on putting LLM coding agents inside a neural network's training loop so they change the architecture mid-training ("mechanistic intervention"), not just the weights. Agents write small programs and insert them into the live network as "code layers" behind a zero-initialized gate, then SGD continues training. On Karpathy's nanochat the agent found a technique doubleAI calls "phantom gradients" (a measure of demand in the network unmet by SGD) to choose and rank candidate code layers.
- **Reported results (publisher):** nanochat loss fell below ordinary training after each new code layer. CLRS-Text algorithmic reasoning accuracy 55% to 84% overall, and 33% to 79% on unseen input sizes. Inserting code layers at the start of training instead of later dropped recall from 72% to 55%. DeepSeek-V4.1-Flash acting as the agent on itself (it located hidden-state signals of wrong answers and wrote a code layer predicting such failures) raised AIME 2026 + HMMT 2026 score from 64% to 71%.
- **License / code:** Blog post only. No code repo, weights, or paper from doubleAI linked on the blog page at pull time; the blog links to public tools it built on (`karpathy/nanochat`, `karpathy/autoresearch`, `deepseek-ai/DeepSeek-V4.1-Flash-1017`, `Qwen/Qwen3-8B`, MathArena AIME/HMMT 2026 datasets).
- **Size and hardware:** Not stated in the thread.
- **Release:** doubleAI research blog, Nov 2026 (thread Nov 6 2026 9:52am CT). Project led by @AlonVin. doubleAI describes itself as "the frontier AI lab for the hardest problems in science and engineering" (makers of Maxwell and Double Agent).
- **Links:** https://www.doubleai.com/research/can-llms-redesign-themselves-as-they-train · https://www.doubleai.com/research · https://github.com/karpathy/nanochat
