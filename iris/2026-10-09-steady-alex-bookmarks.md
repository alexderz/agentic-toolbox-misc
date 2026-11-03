# @Steady_Alex bookmark scan, Oct 9 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Fri Oct 9, 2026 ~9:47am CT. Baseline: [Oct 7 delta](2026-10-07-steady-alex-bookmarks.md) (52 total) on main. Oct 8 routine run failed; this is a full fresh pull.

## Summary

- **Total bookmarks:** 56 (one page, `result_count` 56, no `next_token`, page size 100).
- **New vs Oct 7 baseline:** 4 ids. All 52 baseline ids still present.
- **Memes skipped:** none new (Memes folder still holds only the Oct 5 skip, 2107021822155985254).
- **Folders:** one new folder, **Keep an eye on this** (2108226850757480512), holding Herald OS. Cool tech to try now has 5; Moodils now has 7; Cyber and Memes unchanged.

## Cool tech to try

### Step 5 Preview free for a week on OpenCode

@opencode, posted Oct 8 9:43am CT. OpenCode Zen is offering StepFun's Step 5 Preview free for about a week (free window started Oct 8, expected to end around Oct 15). Model id `step-5-preview-free` / `opencode/step-5-preview-free`: 1M context, multimodal (text, image, video), tool calling, zero data retention. StepFun describes it as a sparse MoE (~600B total / ~27B active) aimed at software engineering and knowledge work, with open weights planned around Oct 15. Same promo pattern as the earlier Space Bunny free week (Oct 3 catalog).
https://x.com/opencode/status/2108206631859454383

**Access:**

- OpenCode models list: https://opencode.ai/docs/models/
- Model card / specs: https://models.opencode.ai/models/stepfun/step-5-preview/
- Zen API endpoint (OpenAI-compatible): `https://opencode.ai/zen/v1/chat/completions`, model `step-5-preview-free`
- Signup / auth: https://opencode.ai/auth
- Hugging Face: no public Step 5 weights yet (org https://huggingface.co/stepfun-ai exists; a Step-5 model page was not publicly readable). Weights said to land around Oct 15.

### Unsloth: train your own Decision model like Jev locally

@UnslothAI, posted Oct 7 11:21am CT. Unsloth added Decision-model training: fine-tune small LLMs (Qwen3.5, Llama 3.2, Gemma 4, etc.) with a Clef-style head so they return typed choices with probabilities instead of text. They report Qwen3.5 0.8B rising from 20.7% to 74.3% aggregate across three decision benchmarks on 4GB VRAM (~42 min). Desktop Train tab ("Train as" → Decision model) or `FastDecisionModel` / `DecisionTrainer` in code; serve through Unsloth's Decision API with Jev-compatible ids (`jev-latest`, `laya`, `default`). Directly continues the Decision / Jev cluster (Decision 2.0, Liquid d1, Cloudflare Clef).
https://x.com/UnslothAI/status/2107868866361930236

**Access:**

- Guide: https://unsloth.ai/docs/basics/train-your-own-decision-model-with-unsloth
- Serve locally (Laya / Jev API): https://unsloth.ai/docs/models/decision-laya
- Source: https://github.com/unslothai/unsloth
- Hugging Face base (example): https://huggingface.co/unsloth/Qwen3.5-0.8B
- Desktop install: https://unsloth.ai (install scripts linked from the guide). No separate paid API required for local train/serve; Colab/Kaggle notebooks are free with a Google account.

## Keep an eye on this (new folder)

### Herald OS — agent-native desktop around Hermes Agent

@iamlukethedev, posted Oct 7 4:30am CT. Independent MIT-licensed desktop that puts Nous Research's Hermes Agent at the center of the OS (not another chat app): talk or type, and the agent works across the machine with a permission layer. Runs a standard Hermes install plus a `herald-os-bridge` plugin; not affiliated with, sponsored by, or endorsed by Nous Research. Still needs a model provider (Nous Portal, OpenRouter / OpenAI / Anthropic key, or a local model), so usage can cost money depending on the brain. Alpha (v0.1.0-alpha.1 era); Linux-focused, MIT.
https://x.com/iamlukethedev/status/2107765448343261506

**Access:**

- Source: https://github.com/iamlukethedev/Herald-OS (MIT)
- Hermes Agent (separate): https://github.com/NousResearch/hermes-agent (MIT)
- Not a model, so no Hugging Face entry. Bring-your-own model/API.

## Moodils

### Project Maya — GLM-5.3-Flash 321B on your own GPU(s)

@PeasantSmith, posted Oct 7 9:42am CT. Open-source stack to run Z.ai's GLM-5.3-Flash (321B MoE, ~18B active, multimodal, up to 1M context, MIT) on one or more NVIDIA GPUs by paging hot experts in VRAM and the rest in RAM / NVMe. Ships Maya GGUF quants (Maya-S ~96.5 GB default, plus S24 / M / L) built from Z.ai's own FP8 release, a browser dashboard, and OpenAI- and Anthropic-compatible APIs. Author cites up to ~40 tok/s decode and hundreds of tok/s prefill on 2× Tesla V100 32GB + ~30 GB RAM. Continues the "huge MoE on consumer / lab GPUs via expert offload" theme (Strata, Bonsai, NVFP4 Flash-Next).
https://x.com/PeasantSmith/status/2107843949184393514

**Access:**

- Project / engine: https://github.com/mw00/project-maya
- Hugging Face quants: https://huggingface.co/peasantsmith/GLM-5.3-Flash-Maya-GGUF
- Base model (official): https://huggingface.co/zai-org/GLM-5.3-Flash
- Z.ai (hosted / product): https://z.ai · chat: https://chat.z.ai
- Open weights under MIT; ~95–156 GB download depending on quant. No API signup required for local Maya.
