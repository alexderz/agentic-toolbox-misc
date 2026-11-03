# @Steady_Alex bookmark scan, Oct 31 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Sat Oct 31, 2026 ~9:15am CT. Baseline: [Oct 30 scan](2026-10-30-steady-alex-bookmarks.md) (125 total).

## Summary

- **New vs baseline:** 5 ids (all above the Oct 30 set on page 1).
- **Total:** 130 if no baseline ids were removed.
- **Memes skipped:** none.
- **Folders:** no new folders (still Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). Moodils +2, Keep an eye on this +1, Cool tech to try +1, unfiled 1.

## Moodils

### Qwen3.5-4B-3D-Coder (CCORE)
@dextune, Oct 30 8:43am CT. https://x.com/dextune/status/2116164031488868393
- **What it is:** independent fine-tune of Qwen/Qwen3.5-4B (not an official Qwen release) by CCORE, an early preview aimed at general coding and Three.js 3D scene generation (HTML/JS output in chat mode). Oct 29 update published full FP16 weights, the training dataset and a technical report; Oct 30 update added optional vision input via the stock Qwen3.5-4B BF16 mmproj (~644 MiB).
- **Training (card/post):** 4,146 synthetic examples (3,933 train / 213 val), about 60 hours, full fine-tune plus a short LoRA stage. Card recommends a specific Three.js system prompt and sampling (temp 0.6, top-k 20, top-p 0.95).
- **License:** Apache-2.0 (model); dataset MIT.
- **Size:** 4.54B params; FP16 safetensors 4 shards ~9.1 GB; GGUF Q4_K_M 2.71 GB, Q8_0 4.48 GB. Tested with llama.cpp b11889 and Transformers 5.20.2. Community GGUFs also on HF (prithivMLmods, ReallyFloppyPenguin).
- **Release:** HF repo created Oct 25 2026, Oct 27 checkpoint update, FP16/dataset/report Oct 29, vision Oct 30.
- **Links:** https://huggingface.co/ccore/Qwen3.5-4B-3D-Coder · dataset https://huggingface.co/datasets/ccore/ThreeJS-3D-Scenes · report https://huggingface.co/ccore/Qwen3.5-4B-3D-Coder/blob/main/Qwen3.5-4B-3D-Coder_Technical_Report.pdf · https://huggingface.co/prithivMLmods/Qwen3.5-4B-3D-Coder-GGUF

### Huihui-DeepSeek-V4.1-Flash-1017-abliterated-GGUF, Unsloth patch (huihui.ai)
@support_huihui, Oct 26 11:59pm CT. https://x.com/support_huihui/status/2114945182332530732
- **What it is:** abliterated (uncensored) GGUF of deepseek-ai/DeepSeek-V4.1-Flash-1017, made directly on GGUF with llama.cpp's cvector-generator. Only layers 11–28 ablated (18 attn_output_b tensors); experts untouched. Post announces Unsloth's other quant levels converted to "patch" files that the user applies locally to Unsloth's GGUFs, instead of full uploads; Maya (Project Maya) and Strata (ISTA-DASLab GSQ-RCO) variants are also shipped as patches.
- **License:** MIT (same tag as base).
- **Size:** full UD-IQ1_M 250.4 GB and UD-IQ1_S 233.0 GB; patch folders unsloth 4.4 GB, Maya 1.8 GB, Strata 1.2 GB; mmproj-BF16 0.97 GB. Requires llama.cpp b11870 or newer.
- **Release:** HF repo created Oct 25 2026, last modified Oct 29.
- **Links:** https://huggingface.co/huihui-ai/Huihui-DeepSeek-V4.1-Flash-1017-abliterated-GGUF · Unsloth patch folder https://huggingface.co/huihui-ai/Huihui-DeepSeek-V4.1-Flash-1017-abliterated-GGUF/tree/main/unsloth · base https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017

## Keep an eye on this

### Android AppFunctions ("Android MCP") beta (Android Developers)
@AndroidDev, Oct 29 5:41pm CT (#AndroidDevSummit). https://x.com/AndroidDev/status/2115937049630916872
- **What it is:** Android platform API plus Jetpack library that lets an app expose functions as on-device tools (the Android equivalent of MCP tools) for agents, apps and assistants such as Gemini. Callers need the `EXECUTE_APP_FUNCTIONS` permission. Post says it is officially in beta; the docs page still labels it experimental preview. Gemini integration is in private preview with trusted testers; end-to-end access is through an Early Access Program.
- **Requirements:** Android 16 or higher; testing via `adb shell cmd app_function ...`. Google also published an AppFunctions agent skill and a sample.
- **License / pricing:** platform API; no pricing. License not stated on the overview page.
- **Release:** docs page last updated Oct 22 2026; beta announced at Android Dev Summit Oct 29.
- **Links:** https://developer.android.com/ai/appfunctions

## Cool tech to try

### OpenBonsai (esokullu / webbrain-one)
@ai_hakase_, Oct 30 12:03am CT. https://x.com/ai_hakase_/status/2116033108491288675
- **What it is:** open post-training quantization framework that compresses a dense BF16 model to ternary weights {-1, 0, +1} in Prism ML's PTQ1_0 GGUF format (Ternary Bonsai layout). Pipeline: signed Hadamard rotation, sequential GPTQ, fp16 scale per 128 weights, scale distillation against the BF16 model's top-64, calibration on the model's own reasoning traces (AYOT, from the ScaleQ-1.58 paper). Independent project, not affiliated with Prism ML. Research preview.
- **Results (README):** OpenBonsai Qwen3.5-9B, thinking off, GSM8K 65/100 and HumanEval 34/50, vs official Ternary Bonsai 77/100 and 45/50. Measured on Qwen3.5-9B and Qwen3-8B.
- **License:** Apache-2.0 (code and model).
- **Size and hardware:** Qwen3.5-9B (~18 GB BF16) to 1,997,486,976-byte GGUF (~2 GB). Compression ~5 hours on one RTX 5090 (32 GB VRAM). Inference needs Prism's llama.cpp fork (upstream llama.cpp does not support PTQ1_0); tested CPU build at commit c9c34bc. Python 3.12, PyTorch 2.14.1, transformers 5.20.2.
- **Release:** GitHub repo created Oct 26 2026; HF model second release Oct 28–29 (first release kept at tag `reasoning-mix-v1`).
- **Links:** https://github.com/esokullu/openbonsai · https://huggingface.co/webbrain-one/openbonsai-qwen-3.5-9b · Prism fork https://github.com/PrismML-Eng/llama.cpp

## Unfiled

### Unsloth Dynamic v3.1 GGUFs for DeepSeek-V4.1-Flash-1017 (Daniel Han / Unsloth)
@danielhanchen, Oct 30 8:36am CT, quoting @UnslothAI (Oct 30 8:13am CT, https://x.com/UnslothAI/status/2116156587404562491). https://x.com/danielhanchen/status/2116162363313525191
- **What it is:** new Unsloth Dynamic v3.1 GGUF quants of DeepSeek-V4.1-Flash-1017 (748B multimodal MoE, released by DeepSeek Oct 17). Unsloth reports v3/v3.1 beat ISTA-DASLab GSQ-RCO quants on GPQA Diamond, AIME25, LiveCodeBench v6, MMLU-Pro, Aider Polyglot, HMMT 2026, IFEval, and says it could not reproduce GSQ-RCO's numbers (1-bit AIME25 91.88%, not 100%). AIME25 run 16× per question. Blog also reports lower-bit quants produce somewhat longer reasoning.
- **License:** MIT.
- **Size and hardware:** UD-IQ1_S 233.0 GB, UD-IQ1_M 250.4 GB, UD-IQ2_XXS 300.5 GB, UD-Q2_K_XL 334.8 GB, UD-IQ3_XXS 394.7 GB, UD-IQ3_S 423.6 GB, UD-Q3_K_XL 485.1 GB, UD-Q4_K_XL 500.7 GB, UD-Q8_K_XL 508.4 GB; plus dspark Q8_0 draft 8.0 GB, mmproj ~0.97 GB, engram folder. UnslothAI post: 64 GB+ RAM (with Engram n-gram offloading). Model card: 128 GB+ RAM for 1-bit, 256 GB for 3-bit, 320 GB for full precision. Needs Unsloth's llama.cpp PR or Unsloth Desktop.
- **Release:** HF repo created Oct 17 2026, v3.1 files Oct 30.
- **Links:** https://huggingface.co/unsloth/DeepSeek-V4.1-Flash-1017-GGUF · guide https://unsloth.ai/docs/models/deepseek-v4.1-flash · reasoning-length section https://unsloth.ai/docs/models/deepseek-v4.1-flash#quantization-increases-reasoning-lengths · base https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017
