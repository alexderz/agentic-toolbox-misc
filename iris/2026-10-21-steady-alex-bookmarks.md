# @Steady_Alex bookmark scan, Oct 21 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Wed Oct 21, 2026 ~9:15am CT. Baseline: [Oct 20 delta](2026-10-20-steady-alex-bookmarks.md) (89 total, newest id 2112232671023644743).

## Summary

- **New vs baseline:** 6 ids (newest 10 bookmarks read; the 7th through 10th were already filed).
- **Total:** 95 if no baseline ids were removed (full list not re-paged this run).
- **Memes skipped:** none new.
- **Folders:** no new folders. Moodils +3 (Ornith-1.5-122B, Ornith DFlash 2 drafter, Unsloth DeepSeek-V4.1-Flash-1017 GGUF); Keep an eye on this 8 → 10 (DeepInfer, FlashMap); Cool tech to try 14 → 15 (Cua Spaces with Hermes); Cyber 2; Memes 2.

## Moodils

### Ornith-1.5-122B — MIT open-weight 122B MoE from Ornith AI

@NeoAIForecast (Neo), posted Oct 20 3:49pm CT. Post text: "A 122B open model that fits on one box." MIT license, weights on Hugging Face; lab evals SWE-bench Verified 84.5 (Qwen3.8-Flash-Next 82.8), BrowseComp 78.5, SWE-bench Pro 76.9 vs 43.9 for Qwen3.8-Flash-Next; notes these are lab numbers, not independent.
https://x.com/NeoAIForecast/status/2112647434702836015

- **What it is:** reasoning model (opens with a think block) in the Ornith-1.5 family. HF card: 122B MoE (`qwen3_5_moe` architecture; 125.1B BF16 params in safetensors), image-text-to-text / text-generation, tool calling. Ornith-1.0 was built on Qwen3.5 and Gemma4 with further pre-, mid- and post-training; 1.5 adds a self-improvement RL loop that generates its own training tasks, scaffolds and rollouts.
- **Card benchmarks (Ornith-1.5-122B / Qwen3.8-Flash-Next):** TerminalBench 2.1 81.2 / 83.4; SWE-bench Pro (no-hack) 76.9 / 43.9; SWE-bench Verified 84.5 / 82.8; SWE-bench Multilingual 76.4 / 73.0; HLE with tools 48.0 / 38.0; BrowseComp 78.5 / 75.3; MCP-Atlas 74.6 / 74.1; Toolathlon-Verified 70.8 / 71.4. Card also compares Qwen3.8 27B, Nemotron 3.5 Super VL, DeepSeek-V4-Flash-0731 and Beam.
- **Context:** 262,144 tokens native; YaRN factor 4 documented for up to ~1M.
- **Sizes (HF):** BF16 repo 250.2 GB; FP8 133.0 GB; NVFP4 77.7 GB; MLX 8-bit 129.8 GB; MLX 4-bit 68.7 GB; GGUF Q4_K_M 75.8 GB, Q5_K_M 88.7 GB, Q6_K 102.4 GB, Q8_0 132.6 GB, BF16 249.4 GB.
- **Hardware / runtime (card):** card states it serves on a single 80 GB GPU (add tensor parallel to shard). Needs Transformers ≥ 5.8.1, vLLM ≥ 0.19.1, or SGLang ≥ 0.5.9; OpenAI-compatible server recipes given. Card mentions a quantized "Ornith-1.5-122B-Mobile" variant; no repo by that name was listed under ornith-ai at pull time.
- **License:** MIT (all ornith-ai 122B repos above tagged MIT).
- **Release:** HF repo created Oct 16 2:14am CT, last modified Oct 21 3:29am CT; FP8 / NVFP4 / GGUF / MLX repos created Oct 19 ~8:09pm CT, MLX 4/8-bit Oct 20 2:00am CT. Publisher Ornith AI (`ornith-ai`, X @ornith_). Earlier family: 1.0 (9B/35B/397B, June 2026), 1.5 9B / 35B-A3B / 397B (Aug 18 2026).

**Links:**

- HF: https://huggingface.co/ornith-ai/Ornith-1.5-122B
- HF GGUF: https://huggingface.co/ornith-ai/Ornith-1.5-122B-GGUF
- HF FP8: https://huggingface.co/ornith-ai/Ornith-1.5-122B-FP8
- HF NVFP4: https://huggingface.co/ornith-ai/Ornith-1.5-122B-NVFP4
- HF MLX 4-bit: https://huggingface.co/ornith-ai/Ornith-1.5-122B-MLX-4bit
- Blog: https://ornith.ai/ornith_1_5.html

### Ornith-1.5-122B-DFlash2 — Inco AI DFlash 2 speculative-decoding drafter

@inco_ai (Inco AI), posted Oct 20 11:07am CT. Post text: congrats to @ornith_ on Ornith-1.5-122B; Inco trained a DFlash 2 drafter for day-0 support; up to 3× faster generation, lossless.
https://x.com/inco_ai/status/2112576331850682540

- **What it is:** draft model (not standalone) for speculative decoding of `ornith-ai/Ornith-1.5-122B`. DFlash 2 is a block-diffusion drafter: predicts a whole block of tokens in one pass, keeps top candidates per position, and a selector traces one path; two-tap dynamic convolutions in the backbone. Greedy output matches the target exactly; sampling preserves its distribution.
- **Size:** 0.93B params, 1.9 GB repo.
- **Runtime:** SGLang 0.5.21 with `--speculative-algorithm DFLASH --speculative-draft-model-path incoai/Ornith-1.5-122B-DFlash2 --speculative-num-draft-tokens 16`; card example uses `--tp 2`.
- **Card results (2× NVIDIA GB300, TP2, block 16, thinking on):** acceptance length GSM8K 8.33, MATH-500 9.20, HumanEval 8.64, MBPP 6.37, MT-Bench 5.41. Throughput speedup vs autoregressive: concurrency 1 1.34–2.65× (e.g. MATH-500 265.8 → 705.5 tok/s); concurrency 32 1.35–2.98×.
- **License:** Apache-2.0 (drafter). Base DFlash code (z-lab/dflash) MIT.
- **Release:** HF repo created Oct 19 5:00am CT, last modified Oct 20 11:01am CT. DFlash 2 blog dated Aug 2026 (Inco AI); original DFlash paper by Chen, Liang, Liu (ICML 2026); z-lab/dflash v0.1.0 Aug 18 2026.

**Links:**

- HF: https://huggingface.co/incoai/Ornith-1.5-122B-DFlash2
- Blog: https://inco.ai/blog/dflash2/
- GitHub (DFlash): https://github.com/z-lab/dflash
- Quoted Ornith post: https://x.com/ornith_/status/2112553477457268799

### Unsloth DeepSeek-V4.1-Flash-1017 GGUF — local run guide and dynamic quants

@UnslothAI (Unsloth AI), posted Oct 19 11:01am CT. Post text: DeepSeek V4.1-Flash-1017 can now run locally; 1-bit retains ~88.2% accuracy while shrinking from 508 GB to 250 GB (−52%); run on a 128 GB+ RAM device; links guide and GGUF; quotes DeepSeek's release post.
https://x.com/UnslothAI/status/2112212605930778830

- **What it is:** Unsloth Dynamic GGUF quants of `deepseek-ai/DeepSeek-V4.1-Flash-1017` (748B MoE, image-text-to-text), with Engram n-gram tables offloaded separately and a DSpark drafter GGUF.
- **Quant sizes (HF folders):** UD-IQ1_S 233.0 GB, UD-IQ1_M 250.4 GB, UD-IQ2_XXS 300.5 GB, UD-Q2_K_XL 334.8 GB, UD-IQ3_XXS 394.7 GB, UD-IQ3_S 423.6 GB, UD-Q3_K_XL 485.1 GB, UD-Q4_K_XL 500.7 GB, UD-Q8_K_XL 508.4 GB. Engram folder 609.8 GB (card: swap MXFP8 engram for Q6_K / Q5_K / IQ4_NL). DSpark drafter Q8_0 8.0 GB; mmproj BF16/F16 1.0 GB each.
- **Hardware (card):** 128 GB+ RAM for the smallest 1-bit; 3-bit on 256 GB; full precision on 320 GB. Runs with Unsloth's llama.cpp PR or the Unsloth Desktop app.
- **License:** MIT (base model MIT).
- **Release:** HF repo created Oct 17 3:36pm CT, last modified Oct 20 5:18am CT. Prior notes on DeepSeek-V4.1-Flash-1017: Oct 18, Oct 20 (Project Maya lists unsloth Q8/Q4 as options).

**Links:**

- HF: https://huggingface.co/unsloth/DeepSeek-V4.1-Flash-1017-GGUF
- Guide: https://unsloth.ai/docs/models/deepseek-v4.1-flash
- Base model: https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017
- Quoted DeepSeek post: https://x.com/deepseek_ai/status/2111375640717033777

## Keep an eye on this

### DeepInfer — DeepSeek's production inference framework, open-sourced

@deepseek_ai (DeepSeek), posted Oct 20 4:30am CT (thread 1/4). Post text: DeepInfer, their in-house inference framework, now fully open source; powers DeepSeek-V4.1-Flash at scale with high throughput and low latency.
https://x.com/deepseek_ai/status/2112476496283775135

- **What it is:** offline-inference release of the framework behind DeepSeek's production services. Supported model: DeepSeek-V4.1-Flash (default checkpoint DeepSeek-V4.1-Flash-1017). Features: kernels (FlashMLA, DeepGEMM, DeepEP, TileKernels, DeepSelect), attention DP / balanced CP, MoE EP + EPLB, DSpark drafting with confidence-scheduled verification, SWA bounded replay, async zero-overhead batch scheduler, batch-invariant inference and deterministic sampling (NVIDIA only), structured outputs (regex / JSON schema / EBNF).
- **Not included:** KV cache system, VE/prefill/decode disaggregation, load balancing across DP replicas.
- **Hardware / build:** NVIDIA SM100 GPUs or Huawei Ascend 950 NPUs; Linux, GCC ≥ 13, Python 3.12, CUDA 13 (NVIDIA) or CANN 9.2 (Ascend); build from source with `./build.sh`. Published benchmarks: 4 SM100 GPUs for prefill, 64 for decode.
- **Origin:** originally built primarily on vLLM, with inspiration from SGLang and TensorRT-LLM.
- **License:** Apache-2.0.
- **Release:** GitHub repo created Oct 16 2:47am CT; last push Oct 20 11:55pm CT; no tagged releases; ~17.0k stars at pull time.

**Links:**

- GitHub: https://github.com/deepseek-ai/DeepInfer
- Default checkpoint: https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017

### FlashMap — flow-map speculative decoding (>6× on Qwen3-8B)

@jeff_shen_ (Jeff Shen), posted Oct 19 10:06pm CT. Post text: FlashMap, a speculative decoding algorithm based on flow maps; >6× faster inference on Qwen3-8B; with @Jay41969851 @_ryantlee @jonathanmay @cosmo_shirley.
https://x.com/jeff_shen_/status/2112379880390131738

- **What it is:** lossless speculative-decoding drafter that samples a whole block of K tokens jointly in one forward pass of a flow map (a DiT cross-attending to a few layers of target hidden states, using the target's frozen embedding and LM head). Target verifies all K in one pass and keeps the longest agreed prefix, so output matches the target exactly (sampling at temperature > 0 follows the target distribution). Positioned against DFlash, which predicts block positions independently.
- **Models:** drafters for Qwen3-8B (0.50B params, 1.0 GB) and Qwen3-4B (0.47B params, 0.95 GB). Project page demo: Qwen3-8B on 1× H100 SXM, greedy, concurrency 1.
- **Runtime:** `pip install flashmap` (Transformers reference); `flashmap[vllm]` with vLLM 0.31.x (`--speculative-config` with 16 speculative tokens); `flashmap[sglang]` with SGLang 0.5.20 (`--speculative-algorithm DSPARK`).
- **Authors:** Jeff Shen, Zhejian Zhou, Ryan Lee, Jonathan May, Shirley Ho (Polymathic AI, Princeton, USC ISI, NYU, Flatiron Institute).
- **License:** code MIT; HF drafters Apache-2.0.
- **Release:** arXiv 2610.24365 submitted Oct 16 8:32pm CT; GitHub repo created Oct 13, last push Oct 19 8:43pm CT; HF models created Oct 15 9:21am CT.

**Links:**

- Project page: https://jshen.net/flashmap/
- arXiv: https://arxiv.org/abs/2610.24365
- GitHub: https://github.com/al-jshen/flashmap
- HF collection: https://huggingface.co/collections/j-shen/flashmap-6ad0feb955bdc30db59769fa
- HF (Qwen3-8B drafter): https://huggingface.co/j-shen/FlashMap-Qwen3-8B
- HF (Qwen3-4B drafter): https://huggingface.co/j-shen/FlashMap-Qwen3-4B

## Cool tech to try

### Cua Spaces — Hermes agent can launch Spaces on your own computers

@trycua (Cua), posted Oct 20 12:00pm CT (thread 1/). Post text: Hermes can now launch Cua Spaces; when a task needs a computer, Hermes creates a Space on your Mac, Windows PC or Linux box, does the work there, and deletes it when done; you and your team can join the same Space while it works. 19 s video.
https://x.com/trycua/status/2112589741879328979

- **What it is:** Cua Spaces turns Macs, Linux boxes and cloud VMs a team already has into shared desktops where agents work and people can watch or step in ("bring your own computers"; Cua does not rent machines). Part of the trycua/cua open-source computer-use stack (drivers, cross-OS sandboxes, benchmarks). "Hermes" here is Nous Research's Hermes Agent: Cua's agent-setup tool writes Cua skills to `~/.hermes/skills` and a `cua mcp` server entry under `mcp_servers` in `~/.hermes/config.yaml`.
- **Platforms:** desktop app for Mac, Linux, and Windows (Windows in preview).
- **Pricing (cua.ai/pricing):** Free $0 (no account needed; up to 2 live sessions and 20 remote hours/month). Pro $15/month yearly ($180) or $18 monthly (5 live sessions, 200 remote hours). Teams $25/seat/month yearly ($300) or $30 monthly, 1–100 seats (each seat adds 5 sessions / 200 hours to a shared pool; shared computers, roles, device approval).
- **License:** trycua/cua repo MIT.
- **Release:** Cua Spaces v0.12.0 published Oct 20 5:18pm CT (five more UI languages, per-machine health issues, `cua doctor --machine`, Cua Driver reliability on Windows/Linux, refuses two compromised eMudhra intermediate certs); v0.12.1 Oct 20 7:31pm CT; cua-spacesd 0.6.0 Oct 20 5:50pm CT. Repo created Jan 2025, ~30.5k stars at pull time.

**Links:**

- Site: https://cua.ai
- Pricing / downloads: https://cua.ai/pricing
- GitHub: https://github.com/trycua/cua
- Releases: https://github.com/trycua/cua/releases
- Hermes Agent docs: https://hermes-agent.nousresearch.com/docs/getting-started/installation
