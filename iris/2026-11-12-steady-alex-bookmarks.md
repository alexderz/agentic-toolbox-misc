# Steady_Alex bookmarks — 2026-11-12

## 12am CT run

### Post by @Da7_Tech (Da7em) on distillation by Chinese labs
- Post: https://x.com/Da7_Tech/status/2120540672696451162 (posted 2026-11-11 15:34 UTC)
- What it is: Opinion/claims thread-length post. The author states a large Chinese lab asked for help distilling "Fable" into its model and that he declined, suggesting public-domain books as training data instead.
- Claims in the post: Kimi K3.1 Pro is not a large leap over Kimi K3 after ~100 days; DeepSeek has not released a Pro model; Zai has gone ~3 months without a new flagship; Qwen 4 Max is described as a letdown; Kimi K3.1 Pro and DeepSeek Flash are said to show traces of "Astra" distillation (author cites a leak naming Moonshot and DeepSeek).
- Model/code release: none. No Hugging Face or repo link in the post. Unverified claims from a single author.

## 4pm CT run

### MACaQ (Model Agnostic Calibrated Quantization) — Huawei Computing Systems Lab
- Post: https://x.com/TeksEdge/status/2120932135724884318 (@TeksEdge, 2026-11-12 17:30 UTC)
- What it is: Open-source post-training quantization toolkit (MXFP4 W4A4 weights+activations; 2/3/4-bit GGUF for llama.cpp). Calibrates each linear layer independently (per-channel scaling, block-Hadamard transform, Hessian-aware Flip-Refinement of FP4 codes). Works on text, image, video, audio models via llama.cpp, vLLM, Diffusers, PyTorch. MACaQ-R refines existing GGUFs while keeping standard llama.cpp compatibility; full MACaQ uses a modified llama.cpp runtime.
- Code: https://github.com/huawei-csl/MACaQ
- Blog: https://huawei-csl.com/blog/macaq/
- Paper: https://arxiv.org/abs/2611.10649 (HF paper page: https://huggingface.co/papers/2611.10649); authors Lorenz K. Muller, Philippe Bich, Chiara Boretti, Hyun-Min Chang, Jiawei Zhuang, Lukas Cavigelli.
- License: Apache 2.0 (code).
- Hardware/size: quantizes a 122B-parameter model in 64 min using 32.5 GB GPU memory (one layer resident at a time); llama.cpp backend also runs on CPU; Python 3.12, separate env per backend. Paper: 2.3% end-to-end overhead over pure MXFP4 on Qwen3-32B in vLLM; lower perplexity than DuQuant++ and MR-GPTQ; matches their best Llama-3-8B perplexity in 11x less quantization time.
- Community test in post (Qwen3-4B IQ4_XS, mean KL divergence): MACaQ 2.260 GB / 0.02804; Bartowski 2.271 GB / 0.03443; Unsloth 2.271 GB / 0.03663.

## 8pm CT run (Nov 12, 2026)

### will depue: checkpoint forensics on Chinese open-weights models (unfiled folder)
- **What it is:** Post claiming a forensic method that matches the initial-weight pattern of a published model to the GPU type and seed that initialized it. Per the post: 6 trillion GPU-layout/seed combinations searched; six Chinese models (incl. DeepSeek-V4-Pro, Kimi K3, MiniMax-M3) matched NVIDIA Blackwell systems (four match Grace Blackwell GB200/GB300); a B300 reproduced DeepSeek-V4-Flash's initial weights bit for bit (seed 953049583) and a rented GB200 reproduced Kimi K3's at 0.999995 correlation; H100 did not match; method matched 24 known models to their stated hardware; author states independent verification by senior researchers at OpenAI and Anthropic. Author's estimate: 2,000–3,000 Blackwell GPUs each for Kimi K3 and DeepSeek-V4-Pro. Claims are the author's, not independently confirmed here.
- **Links:** post https://x.com/willdepue/status/2120992457630326841 · report http://unemploymentlabs.com/checkpoint-forensics (returned HTTP 500 when fetched at filing time)
- **License / size / hardware:** none (research report, no released model).
- **Release:** will depue (@willdepue), posted Nov 12, 2026 ~3:29pm CT.

### Perplexity pplx-decider-v1.3 and pplx-decider-flash-v1.3 (Perplexity CEO's post quoting @perplexitydevs)
- **What it is:** Open-weight "decision" models (classification / extraction). v1.3 adds "locate": describe what to find and the model returns matching text with character offsets. Vendor-reported: on 17 out-of-domain NER, PII and extractive QA tasks they outperform the best general extraction model; on 63 production classification tasks v1.3 is 6.54 points more accurate than Perplexity's current classifiers. Free on OpenRouter for one week.
- **Links:** post https://x.com/AravSrinivas/status/2121020114321703210 · announcement https://x.com/perplexitydevs/status/2120948200232419356 · blog https://www.perplexity.ai/hub/blog/perplexity-decider (Cloudflare challenge at fetch time) · HF https://huggingface.co/perplexity-ai/pplx-decider-v1.3 · HF https://huggingface.co/perplexity-ai/pplx-decider-flash-v1.3 · also in Perplexity Decisions API and OpenRouter
- **License:** Apache-2.0.
- **Size and hardware:** v1.3 ~26.1B params (safetensors total 26,085,330,160), fine-tune of Qwen/Qwen3.8-27B; flash-v1.3 ~4.54B params, fine-tune of Qwen/Qwen3.5-4B.
- **Release:** Perplexity; HF repos created Nov 9, 2026, last modified Nov 10, 2026; announced Nov 12, 2026.
