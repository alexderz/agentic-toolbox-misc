# @Steady_Alex bookmark scan, Oct 26 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Mon Oct 26, 2026 ~9:25am CT. Baseline: [Oct 24 delta](2026-10-24-steady-alex-bookmarks.md) (104 total, newest filed id 2113694480650166428). Oct 25 run: no change.

## Summary

- **New vs baseline:** 2 ids (newest 15 bookmarks read; the 3rd onward were already filed).
- **Total:** 106 if no baseline ids were removed (full list not re-paged this run).
- **Memes skipped:** none new.
- **Folders:** no new folders (Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). Moodils +2 (both entries below).

## Moodils

### Nanbeige4.3-33B (Nanbeige)

@nanbeige, posted Sun Oct 25 7:11am CT. Post text: announces Nanbeige4.3-33B; strategy "starts with building a powerful teacher first"; claims SOTA agentic performance among open models at ~30B parameters.
https://x.com/nanbeige/status/2114328933181333798

- **What it is (per model card):** 33B dense agent and reasoning model, flagship "teacher" of the Nanbeige4.3 series, aimed at agentic coding and "professional cowork" tasks; card says it will anchor distillation into smaller models (e.g. a planned Nanbeige4.3-3B). Chat template has `enable_thinking` and tool-use options. English and Chinese.
- **Architecture (config.json):** `LlamaForCausalLM`, 52 layers, hidden 7168, 56 attention heads / 8 KV heads, vocab 166,912, max position embeddings 524,288 (512K), BF16.
- **Size:** 33.12B parameters; BF16 safetensors ~66.3 GB. Base model same size.
- **Card benchmarks (vendor's own, highest thinking effort, vs Qwen3.8-27B / Muse-Glimmer-30B / Gemma4-31B):** Terminal-Bench 2.1 80.9 (73.0 / 61.8 / 47.2); SWE-Bench Pro 60.3 (61.7 / 36.9 / 51.2); DeepSWE 65.5; Claw-Eval pass^3 78.3; Toolathlon-Verified 70.4; GDPval 84.8 (Qwen 86.4); GPQA Diamond 89.5 (Gemma 91.3); AIME 2026 95.2; AA-LCR 84.0.
- **License:** Apache-2.0 (instruct and base).
- **Release:** Hugging Face repos created Oct 23 2026 ~9:47–9:49pm CT (Base and instruct); announced on X Oct 25. Earlier Nanbeige line: Nanbeige4.2-3B (Jul 2026), Nanbeige4.1-3B (Feb 2026).

**Links:**

- Model: https://huggingface.co/Nanbeige/Nanbeige4.3-33B
- Base model: https://huggingface.co/Nanbeige/Nanbeige4.3-33B-Base
- Org on Hugging Face: https://huggingface.co/Nanbeige
- Announcement post: https://x.com/nanbeige/status/2114328933181333798

### Nanbeige4.3-33B GGUF quants (AtomicChat)

@atomic_chat_hq (atomic.chat), posted Sun Oct 25 12:54pm CT, replying to @nanbeige: "just made GGUFs for it".
https://x.com/atomic_chat_hq/status/2114415320135819711

- **What it is:** llama.cpp GGUF quantizations of Nanbeige4.3-33B built from the BF16 weights on release day. "Atomic Dynamic" (AD-) files use AtomicChat's own importance matrix (8,000 chunks x 512 tokens); plain llama.cpp `Q8_0` and `Q5_K_M` without imatrix. Card lists KL divergence and top-1 agreement vs BF16 per file (24 chunks x 4,096 tokens, llama.cpp `36e36e6`); `Q8_0` KL 0.0032 / top-1 98.0%, `AD-Q6_K` KL 0.0052 / 97.5%.
- **Files (size on disk):** AD-IQ2_S 13.7 GB, AD-IQ3_XXS 14.9 GB, AD-IQ3_S 17.1 GB, AD-IQ4_XS 20.4 GB, AD-Q4_K_M 21.2 GB, AD-Q5_K_M-Q4_K_M 22.6 GB, Q5_K_M 23.5 GB, AD-Q5_K_M 24.7 GB, AD-Q6_K-Q5_K 27.9 GB, AD-Q6_K 30.1 GB, Q8_0 35.2 GB.
- **License:** Apache-2.0 (inherits base).
- **Release:** repo created Oct 25 2026 9:05am CT, last modified Oct 26 6:37am CT. Card notes plain `Q6_K` and `Q4_K_M` were posted for the first hours and then removed.
- **Runtime:** llama.cpp; also offered in the Atomic Chat app.

**Links:**

- GGUF repo: https://huggingface.co/AtomicChat/Nanbeige4.3-33B-GGUF
- Metrics and imatrix: https://huggingface.co/datasets/AtomicChat/Nanbeige4.3-33B-GGUF-metrics
- Atomic Chat app: https://atomic.chat/
- Atomic Chat GitHub: https://github.com/AtomicBot-ai/Atomic-Chat
- Post: https://x.com/atomic_chat_hq/status/2114415320135819711
