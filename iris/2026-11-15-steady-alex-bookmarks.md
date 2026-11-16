# @Steady_Alex bookmarks, Nov 15, 2026

## 8am CT run (Nov 15, 2026)

One bookmark new since the Nov 14 notes (unfiled folder, 0 memes).

### Nace.AI Qwen GGUF quants via Weight Space Programming (post by @TeksEdge, Nov 14, 2026)
- **What it is:** the post says Nace.AI (maker of the Drex decision models; Drex Max v1.1 shown on the Artificial Analysis Decision Index) spent about 1B AI tokens on Qwen quants, letting frontier AI models (Astra/Fable/Carbon agents per the author) read and edit tensor precisions directly ("Weight Space Programming"): propose precision changes, measure KL divergence, keep or revert each edit. Author's release post (r/LocalLLaMA, Nov 14, 2026): benchmarks on English Wikipedia, chat/tool-call transcripts and GitHub code published after Oct 2026, 512 to 128K tokens. Reported (top-1 agreement with full model at 128K): Qwen3.5-9B Q3_K_XL 90.5% at 4.7 GB; Qwen3.6-35B-A3B Q3_K_S 91.2% at 15.3 GB; Qwen3.8-27B Q4_K_XL 97.7% at 17.3 GB; Qwen3.8-Flash-Next IQ4_XS 93.0% at 93.4 GB. Next-best same-size rivals named: Unsloth, ByteShape, EXL3. Post image: MMLU scores, Nace vs best-KL rival vs full precision (9B IQ2_M 39.3 vs 39.1; IQ3_M 40.2 vs 40.0; Q3_K_XL 40.3 vs 40.0; BF16 40.6; 35B-A3B IQ3_XXS 42.0 vs 41.9; Q3_K_S 42.1 vs 42.2; BF16 42.4; 27B Q4_K_XL 42.9 vs 42.9; BF16 43.0; Flash-Next IQ4_XS 46.4 vs 46.3; Q8_0 46.4). Author notes the method scales less well to larger models; paper stated as coming. Also released: Nace MLX quants for Mac (Qwen3.5-4B/9B, Qwen3.8-27B, Flash-Next KQuant, dated Nov 11, 2026; run on Kapitsa, Nace's Apple-silicon inference).
- **Links:** post https://x.com/TeksEdge/status/2121724857343705176 · HF org https://huggingface.co/nace-ai · GGUF https://huggingface.co/nace-ai/Qwen3.5-9B-GGUF · https://huggingface.co/nace-ai/Qwen3.8-27B-GGUF · https://huggingface.co/nace-ai/Qwen3.6-35B-A3B-GGUF · https://huggingface.co/nace-ai/Qwen3.8-Flash-Next-GGUF · Drex paper https://arxiv.org/abs/2611.07854 · Drex code/weights https://github.com/nace-ai/drex-decision-models · Drex Max v1 (open, 27B) https://huggingface.co/nace-ai/drex-max-v1 · Drex Max v1.1 (API only) https://artificialanalysis.ai/decision-models/drex-max-v1-1 and https://console.nace.ai
- **License:** quants inherit the Qwen base-model licenses (Qwen community license noted on the Flash-Next MLX card; not an official Qwen release). Drex Max v1 under Nace.AI Open RAIL-M; Drex Max v1.1 API-only, $0.03 per 1M input tokens (Artificial Analysis).
- **Size and hardware:** GGUF sizes above (4.7 GB to 93.4 GB); Drex Max v1 27B dense, bf16 about 49 GB, affine Q4 runs on 24 GB Apple-silicon Macs.
- **Release:** Nace.AI (author Alish); GGUF release post Nov 14, 2026; HF repos updated Nov 14, 2026.

## 4pm CT run (Nov 15, 2026)

One bookmark new since the 8am notes (unfiled folder, 0 memes).

### Inkling-2-Small GGUF, ~150 GB IQ2_XXS mix (post by @PeasantSmith, Nov 15, 2026)
- **What it is:** a community GGUF of Thinking Machines' Inkling-2-Small (594B-parameter MoE, 1,048,576-token context, image-text-to-text) for llama.cpp. Routed experts use per-expert error-feedback (GPTQ-style) rounding calibrated layer by layer; gate/up at IQ2_XXS, down projections set per layer by a sensitivity sweep (IQ1_S in 30 layers, IQ1_M in 2, IQ2_XXS in 14, IQ2_XS in 2); attention Q8_0, attention output and output head Q6_K, embeddings Q4_K, router and norms F32. Card figures vs the original model on held-out text (32 x 2048 tokens): 94.3% same top token, mean KLD 0.114, median KLD 0.0026, PPL +3.6%. Runs on llama.cpp PR 32187 (text and vision); the MTP/DSpark draft block is not loaded by that PR (DSpark support is PR 32218 on top of PR 32217, which uses a different GGUF layout; files for it are stated as to follow).
- **Links:** post https://x.com/PeasantSmith/status/2122025487186940397 · HF https://huggingface.co/peasantsmith/Inkling-2-Small-GGUF · base https://huggingface.co/thinkingmachines/Inkling-2-Small · llama.cpp https://github.com/ggml-org/llama.cpp (PR 32187)
- **License:** Apache-2.0 (quant and base).
- **Size and hardware:** 4 language-model shards, 150.0 GB total; mmproj F16 0.66 GB; MTP BF16 3.4 GB. Card example: llama-server with `-ngl 99 -c 32768`, `--n-cpu-moe N` / `--cpu-moe` to keep experts in system RAM.
- **Release:** published by peasantsmith on Hugging Face, last modified Nov 15, 2026; base model by Thinking Machines.

## 8pm CT run (Nov 15, 2026)

One bookmark new since the 4pm notes (unfiled folder, 0 memes).

### Unharnessed, a one-tool (Python REPL) coding-agent harness (post by @RayaneRachid_, Nov 15, 2026)
- **What it is:** a coding-agent harness whose model gets exactly one tool, `ipython`, a persistent CPython REPL (no read/grep/edit/fetch tools; the model writes Python for those and keeps helper functions as variables in the session). Harness in Rust: agent loop, compaction, goals, provider retry/failover, sessions. Ships as a VS Code extension, a headless CLI and an ACP agent. Runs commands with user permissions without prompting; the kernel is not a sandbox (stated in the README). Post claims a new state-of-the-art on Terminal-Bench 4.0; the site reports 47 of 66 tasks passed with Claude Opus 5.5 and a score-versus-cost comparison against Claude Code and Codex. Terminal-Bench 4.0: 66 tasks, 8-hour flat agent timeout, from the Laude Institute/Harbor framework (v4.0.0 released 2026-08-26; v4.1.0 on 2026-11-03).
- **Links:** post https://x.com/RayaneRachid_/status/2122024268368380148 · site https://unharnessed.dev/en · code https://github.com/unharnessed-agent/Unharnessed · Terminal-Bench 4.0 https://www.tbench.ai/news/terminal-bench-4-0
- **License:** MIT (LICENSE file also credits Prime Intellect Ltd. and Mario Zechner portions).
- **Size and hardware:** kernel is a CPython 3.11+ process in a uv-managed venv built on first run; model is provider-supplied (no local weights).
- **Release:** unharnessed-agent GitHub org; repo created 2026-10-02; latest release vscode-v0.0.4 published 2026-11-15.
