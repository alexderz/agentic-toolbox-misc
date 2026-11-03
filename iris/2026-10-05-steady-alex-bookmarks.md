# @Steady_Alex bookmark scan, Oct 5 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Mon Oct 5, 2026 ~5:30pm CT. Baseline: [Oct 3 catalog](2026-10-03-steady-alex-bookmarks.md) (35) + [Oct 4 delta](2026-10-04-steady-alex-bookmarks.md) (39 total) on main.

## Summary

Access URLs (Hugging Face, API, and signup) for the new models are included below, per Alex on Oct 5.

- **Total bookmarks:** 47 (one page, `result_count` 47, no `next_token`, page size 100).
- **New vs Oct 4 baseline:** 8 ids. All 39 baseline ids still present.
- **Memes skipped:** 1 (Memes folder: @moritzkremb "Claude made a video about being European", id 2107021822155985254). Not filed.
- **New non-meme:** 7.
- **Folders (new — first time folders exist):**
  - **Moodils** (2107212657665126892): 6 posts, all new today (models / local LLM).
  - **Cyber** (2107138170575822976): 1 post, new today.
  - **Memes** (2107138069035933856): 1 post, skipped.
  - The 39 baseline bookmarks are unfoldered. Only today's saves are filed into folders.
- **Post dates:** all 8 new posts are Oct 5, 2026, 3:15am–2:11pm CT.

### Topics touched (new only)

- Decision models (Jev niche) — 1
- New model launches — 3
- Local quantization / consumer-GPU MoE — 2
- Cyber / offensive security with AI — 1

## Decision models (Moodils)

### Liquid AI d1 with vision

@liquidai, Oct 5 12:32pm CT. d1, Liquid's first decision model, now takes images, text, or both and returns typed yes/no ("noul"), choice, or score answers with probabilities in one forward pass (no generated tokens). Uses the same System One `/decisions/v1/systemone` schema as TypeSafe's Jev; Liquid's docs show Jev SDKs pointed at Liquid. Claims match/beat GPT-6.1 Sol on 4 of 6 real apps at 19–200x lower cost; text decisions ~200–300ms. API price ~$0.04/M input, $0 output; OpenRouter/Vercel text-only for now (OpenRouter listed Oct 1). Third Jev-schema competitor after Decision 2.0 (Oct 4 delta) and Cloudflare Clef (Oct 3).
https://x.com/liquidai/status/2107161990808674404 · https://www.liquid.ai/blog/d1-decision-model · comparison: https://knowviq.com/blog/decision-models

**Access:**

- Hugging Face: no public d1 weights. A LiquidAI-org search for `d1` returned none. The blog says open weights are planned for upcoming models, not this checkpoint.
- Docs: https://docs.liquid.ai/lfm/models/decision-models — hosted call is `POST https://api.liquid.ai/decisions/v1/systemone`, model `d1`. Vision is the paid `d1`; `d1:free` is text-only.
- Signup / API keys: https://console.liquid.ai (register, then Dashboard > API Keys). Playground: https://playground.liquid.ai
- OpenRouter (text): https://openrouter.ai/liquid/d1
- Vercel AI Gateway (text): https://vercel.com/ai-gateway/models/d1

## New model launches (Moodils)

### Reflection AI Beam (501B / 23B active)

@reflection_ai, Oct 5 2:11pm CT. Sparse MoE, 501B total / 23B active, text-only, 1M context, 23.8T pretraining tokens, heavy RL. Claims GLM-5.2-level reasoning at 3–4x less inference compute; Kimi K3 still ahead. Waitlist beta now; Apache 2.0 weights + tech report "later this month" (October). Not consumer-GPU hostable at full precision.
https://x.com/reflection_ai/status/2107186849370247235 · https://reflection.ai/blog/introducing-beam

**Access:**

- Waitlist / sign-in: https://platform.reflection.ai — the blog’s “sign up” and “waitlist” links both go here. New sign-ups join a waitlist, then create keys.
- API docs: https://developers.reflection.ai/introduction · model list (`Beam-501B-A23B`): https://developers.reflection.ai/models · keys: https://developers.reflection.ai/authentication
- OpenAI-compatible base from those docs: https://api.reflection.ai/openai/v1
- Hugging Face: no public weights. Searches for `Beam-501B` and author `reflection` returned none. The blog still says weights, the tech report, and the model card later this month.

### Reka Rho-1 (19B omni, research preview)

@RekaAILabs, Oct 5 9:41am CT. 19B model trained from scratch that understands and generates text, images, video, and robot actions in one network (actions as continuous tokens; same weights predict next frames and drive motors). Paired with Reka's inverse-dynamics model to label web video with actions. Trained on 320 H100s ~3 months. Research preview only; no public weights/API noted.
https://x.com/RekaAILabs/status/2107118937490006363 · https://reka.ai/labs/research/rho-1-collapsing-the-multimodal-stack

**Access:**

- Hugging Face: no Reka Rho-1 repo (author search returned none).
- Research preview is by request: contact@reka.ai, as printed on the research post. Contact form: https://reka.ai/contact
- Public API docs do not list Rho-1: https://docs.reka.ai/chat/models. https://reka.ai/cloud is the general Cloud page linked from the post; it does not name a Rho-1 signup or model id.

### interfaze-1-lite (open-weight "deterministic work" model)

@interfaze_ai, Oct 5 11:22am CT. Mixture-of-architectures: a Qwen3.8-27B-based reasoning core routes to specialists (OCR with per-word boxes/confidence, Whisper-turbo ASR, pyannote diarization, SAM 2.1, TimesFM forecasting, Llama Guard, GUI grounding). JSON-schema structured output, 131k context, offline on one 80GB GPU (Ada/Hopper). Claimed OCR/grounding/structured-output numbers. `trust_remote_code` required. Also served via Interfaze API.
https://x.com/interfaze_ai/status/2107144505711595575 · https://huggingface.co/interfaze-ai/interfaze-1-lite

**Access:**

- Weights: https://huggingface.co/interfaze-ai/interfaze-1-lite (Apache 2.0).
- Model / self-host docs: https://interfaze.ai/docs/models/interfaze-1-lite
- Chat API docs: https://interfaze.ai/docs/api/chat-completion (model id `interfaze-1-lite`).
- API keys: https://interfaze.ai/dashboard · playground: https://interfaze.ai/dashboard/playground · pricing: https://interfaze.ai/pricing

## Local quantization / consumer-GPU MoE (Moodils)

### Red Hat NVFP4 Qwen3.8-Flash-Next

@RedHat_AI, Oct 5 10:17am CT. NVFP4 checkpoint (MoE experts W4A4 FP4, rest BF16) for vLLM; text/image/video in. Claims 99.1% average accuracy recovery vs Inferact (97.6%) and NVIDIA (98.0%) NVFP4 builds. Still a ~180B-param checkpoint; model card's example serves at tensor-parallel 4. NVFP4 needs Blackwell-class GPUs.
https://x.com/RedHat_AI/status/2107128095354265664 · https://huggingface.co/RedHatAI/Qwen3.8-Flash-Next-NVFP4

**Access:**

- Weights: https://huggingface.co/RedHatAI/Qwen3.8-Flash-Next-NVFP4 · base model: https://huggingface.co/Qwen/Qwen3.8-Flash-Next
- No Red Hat or IBM hosted API on the model card. It is a local vLLM serve of that Hugging Face repo (`vllm serve RedHatAI/Qwen3.8-Flash-Next-NVFP4`).
- vLLM recipe linked from the card: https://recipes.vllm.ai/Qwen/Qwen3.8-Flash-Next

### Strata IQ3_S GSQ-RCO (needmorevram thread)

@needmorevram, Oct 5 5:09am CT. Thread clarifying that Strata's IQ3_S is ISTA-DASLab's GSQ-RCO quant (per-tensor formats under a size budget), not regular IQ3 or Unsloth's. Strata runs Qwen3.8-Flash-Next (125B MoE) on a 12GB+ card by keeping experts in RAM, hot experts in VRAM, a ~29GB n-gram shard on SSD, plus speculative decoding. IQ3_S needs ~54.8GB shard + ~10GB headroom, so 64GB RAM (48GB → IQ2_XS; 32GB → Coder). Download is about 70GB. Reported ~53 tok/s on RTX 5070 12GB; @needmorevram measured 51.8 tok/s on a 4070 Ti SUPER 16GB and ~40 tok/s on 2x RTX 3060 12GB at 256K. Directly continues the Oct 3 "extreme compression" + "consumer-GPU speed" clusters.
https://x.com/needmorevram/status/2107050538311532897 · https://github.com/Niko1221/Strata · https://vramcalculator.com/strata-qwen3-8-flash-next/

**Access:**

- Quant: https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF · IQ3_S shards: https://huggingface.co/ISTA-DASLab/Qwen3.8-Flash-Next-GSQ-RCO-GGUF/tree/main/IQ3_S (card: 3.50 bpw, shard 1 54.8 GB, shard 2 28.8 GB, Apache 2.0).
- Base weights: https://huggingface.co/Qwen/Qwen3.8-Flash-Next
- Size and install notes: https://github.com/Niko1221/Strata/blob/main/docs/MODELS.md

## Cyber (Cyber folder)

### AI in Offensive Cybersecurity, Part II: Attack Surface Mapping

@migtissera (Migel Tissera), Oct 5 9:47am CT. Video + blog: using an AI coding agent (OpenCode or Pi-agent with DeepSeek/GLM/Mimo) to map a web app's attack surface from OpenAPI docs, JS bundles, and browser traffic; finds an undocumented endpoint, builds an inventory (125→129 entries), shortlists 10 for review; sets up SSRF for Part III. Uses an authorized demo app he owns.
https://x.com/migtissera/status/2107120597688033537 · https://learn.drost.ai/articles/attack-surface-mapping/

## Skipped

- Memes folder: one post skipped, not filed.
