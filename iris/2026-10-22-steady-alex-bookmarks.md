# @Steady_Alex bookmark scan, Oct 22 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Thu Oct 22, 2026 ~9:20am CT. Baseline: [Oct 21 delta](2026-10-21-steady-alex-bookmarks.md) (95 total, newest id 2112576331850682540 in feed order).

## Summary

- **New vs baseline:** 1 id (newest 12 bookmarks read; the 2nd through 12th were already filed).
- **Total:** 96 if no baseline ids were removed (full list not re-paged this run).
- **Memes skipped:** none new.
- **Folders:** no new folders (Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). Moodils +1 (Flint).

## Moodils

### Recursive Flint (Flint-40B-A2B) — Apache-2.0 open-weight 40B MoE coding model

@ItsmeAjayKV (AJ), posted Oct 21 1:57pm CT. Post text: another open model release today; Flint-40B-A2B, an MoE model from @Recursive_SI; text in/out, reasoning, multi-turn tool use; max context 262,144; Apache 2.0; 54.9% Terminal-Bench 2.1, 89.7% SWE-bench Pro v2, 74.2% SWE-bench Verified; quantized variants for NVIDIA and Apple Silicon.
https://x.com/ItsmeAjayKV/status/2112981571716415961

- **What it is:** Recursive's mixture-of-experts language model for coding agents, trained from scratch (pretraining, mid-training, SFT, RL). Recursive says its automated-research system ("Eureka Machine") contributed to data, training recipes, infrastructure and inference work, and that the model was built in under four months.
- **Specs (HF card):** 39.8B total params, ~2.5B active per token (incl. output head; ~2.2B body). 49 layers (2 dense + 47 MoE); 35 sliding-window (513-token) + 14 full-attention layers; 32 query / 4 KV heads; 256 routed experts, 6 per token, plus a shared expert. Context 262,144 tokens documented (blog: supports up to 512k, recommends staying within 256k). Vocab 150,144. Text in / text out. Stated knowledge cutoff June 2026.
- **Card benchmarks (Recursive release evals, temp 1.0 / top-p 0.95 / top-k 20, avg pass@1 over ≥5 attempts):** Terminal-Bench 2.1 54.9% (Terminus 2; retrieval-obtained solutions counted as failures); SWE-bench Pro v2 89.7%; SWE-bench Verified 74.2% (mini-swe-agent).
- **Speed (blog):** >125 tok/s on an M4 Pro MacBook Pro and >150 tok/s on a 64 GB NVIDIA RTX Spark at short contexts, with Recursive's inference engine.
- **Checkpoints and sizes (HF):**
  - BF16 `RecursiveSI/flint`: 79.6 GB (15 safetensors shards) plus SGLang serving kit; card says one B300 or H200 GPU per replica; Transformers modeling code not included yet.
  - MLX INT4 `RecursiveSI/flint-int4`: 22.6 GB (group-64 affine INT4, INT8 embeddings), for Apple Silicon.
  - Q4_1 GGUF `RecursiveSI/flint-int4-gguf`: 26.0 GB, llama.cpp + Metal; card requires an Apple Silicon Mac with at least 48 GB unified memory.
  - NVFP4 GGUF `RecursiveSI/flint-nvfp4-gguf`: 22.9 GB, llama.cpp + CUDA; tested on B300, RTX PRO 6000 Blackwell, RTX Spark, DGX Spark; recommends at least 48 GB GPU memory (or unified memory on Spark).
  - llama.cpp needs a release with Flint support.
- **Runtimes (docs):** rec (Recursive's engine, Mac), Ollama, Unsloth, LM Studio, llama.cpp; GPU serving with Transformers, SGLang, vLLM; harness guides for OpenCode, Pi, Cline, OpenHands. Docs list hosted Flint-40B on OpenCode's free tier (capacity/rate limited) and free Flint through Radius for Pi; card notes hosted API terms are separate from the weight license.
- **rec engine:** GitHub `recursive-oss/rec`, Apache-2.0, repo created Oct 21 10:35am CT, v0.1.0 released Oct 21 10:58am CT, 95 stars at pull time.
- **License:** Apache-2.0 (all four HF repos and rec). Recursive site also links model terms.
- **Release:** publisher Recursive (Recursive Superintelligence; HF `RecursiveSI`, X @Recursive_SI). Quant repos created Oct 21 8:51am CT; BF16 repo created Oct 21 9:20am CT. Blog "Introducing Flint" on recursive.com.

**Links:**

- HF (BF16): https://huggingface.co/RecursiveSI/flint
- HF (MLX INT4): https://huggingface.co/RecursiveSI/flint-int4
- HF (INT4 GGUF, Apple Silicon): https://huggingface.co/RecursiveSI/flint-int4-gguf
- HF (NVFP4 GGUF, NVIDIA): https://huggingface.co/RecursiveSI/flint-nvfp4-gguf
- Blog: https://www.recursive.com/updates/introducing-recursive-flint
- Docs: https://docs.recursive.com/getting-started
- GitHub (rec engine): https://github.com/recursive-oss/rec
- Model terms: https://www.recursive.com/legal/model-terms
