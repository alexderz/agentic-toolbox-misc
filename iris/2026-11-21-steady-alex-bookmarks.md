# Steady_Alex bookmarks, 2026-11-21

## 11:50am CT run (6 new bookmarks)

### 1. StrataFlux (post by @swarogan, 2124102691194306800, 2026-11-21 5:28am CT)
- What: Low-bit LLM inference framework. Keeps 2-4-bit weights and 2-3-bit KV cache on GPU; stores higher-precision refinement bits in host RAM or SSD and fetches them selectively, overlapping transfers with generation.
- Post figures (RTX 5090, authors' results): Qwen3-8B at 2-bit weights and KV, AIME 2024/2025 11.0% -> 47.1% with same GPU memory. Llama 3.1 8B at 128K context: vLLM (4-bit W, 8-bit KV) 14.3 GB, 106.8 tok/s; StrataFlux (3-bit W, 2-bit KV) 7.3 GB, 102 tok/s.
- Links: post https://x.com/swarogan/status/2124102691194306800 ; paper https://arxiv.org/abs/2611.08363 (PDF https://arxiv.org/pdf/2611.08363)
- Code repo / HF: none found; web search results state no code release linked in the paper.
- Hardware: needs host RAM or SSD for refinement data; GPU memory is the low-bit model.

### 2. Intel D270 vs NVIDIA RTX PRO 6000 Blackwell (post by @mylifcc, 2123997582825595108, 2026-11-20 10:31pm CT)
- What: Post (Chinese) summarizing an Intel benchmark publication for the D270 (Xe3P) 350W PCIe card vs RTX PRO 6000 Blackwell (600W).
- Per post: 5.9x lead in FP64 option pricing (Monte Carlo 5.9x, Black-Scholes 5.6x, binomial 4.6x); Qwen3-30B-A3B (FP8) output throughput 1.12x RTX PRO 6000; native full-rate FP64; LPDDR5X memory, 160 GB at 1.5 TB/s reference, up to 480 GB on partner boards; SC26 demo with SambaNova SN50 (D270 prefill, SN50 decode). Intel test box per post: 1x D270 + 3x Arc Pro B70; NVIDIA box: 8x RTX PRO 6000.
- Link: post https://x.com/mylifcc/status/2123997582825595108 . Intel's original page not located in this run.

### 3. skill-distill (post by @0xSero, 2124035122924232712, 2026-11-21 1:00am CT)
- What: Skill for Claude Code / Codex (teacher) that turns a good session into a skill an open-weight model/harness (student) can follow; loops with 3 trials per version until student matches the reference.
- Repo: https://github.com/sybil-solutions/skill-distill (MIT; created 2026-11-21 per GitHub API)
- Requirements (README): tmux, git, Python 3.10+, student harness; optional playwright/pillow.
- Post: https://x.com/0xSero/status/2124035122924232712 (has 114s demo video)

### 4. finetune-inkling-2-small skill (post by @migtissera, 2123849865679749342, 2026-11-20 12:44pm CT)
- What: Skill repo to fine-tune Inkling 2 Small with a coding agent: SKILL.md, Python scripts, requirements.txt. Post says it is the recipe used for Tess-4.5-594B-A17B.
- Repo: https://github.com/drost-ai/finetune-inkling-2-small (license not retrieved; GitHub API rate-limited)
- Post: https://x.com/migtissera/status/2123849865679749342

### 5. Hy4 Flash Abliterated GGUF (post by @OrcaRouter, 2124054562202141089, 2026-11-21 2:17am CT; quotes @OrcaCyberHQ 2124053590096630211)
- What: Abliterated / uncensored GGUF quants of Tencent Hy4-Flash (Hunyuan MoE) by OrcaCyber, mixed-precision with imatrix, for llama.cpp.
- HF: https://huggingface.co/orcarouter/Hy4-flash-abliterated-GGUF (created 2026-11-20 9:43pm CT; license tag "other", LICENSE file in repo); base: orcarouter/Hy4-flash-abliterated
- Files: Mix-128G (3 shards, ~138 GB total) and Mix-256G (6 shards, ~238 GB total); repo ~612 GB total. Post says runs on 128GB or 256GB machines.
- Post: https://x.com/OrcaRouter/status/2124054562202141089

### 6. maya-ik2: custom Inkling 2 Mini engine on Project Maya (post by @superalesha, 2124102269138346409, 2026-11-21 5:26am CT)
- What: Custom engine for Inkling 2 Mini built on @PeasantSmith's Project Maya; all 3,072 experts resident in VRAM, 1 CUDA graph (781 launches vs ~7,350), custom Tensor Core kernels for FP8 KV attention and NVFP4 experts; BF16 vision on CPU.
- Post figures, 1x RTX 3090 (300W, Unsloth UD-Q4_K_XL, FP8 KV): 128.7 tok/s decode short vs 57.0 llama.cpp; 4K 124.2 / prefill 2,742 (vs 1,052); 64K 105.6 / 2,361 (vs 42.7 / 630); 128K 90.6 / 2,079; 340K 62.3 / 1,473 at 23.57 GiB peak VRAM, 344K context. GSM8K 74/96 vs 73/96 (KL 5.7e-5).
- Repo: author said commits are being cleaned up for GitHub; no repo link in post.
- Post: https://x.com/superalesha/status/2124102269138346409 (16s video)
