# @Steady_Alex bookmark scan, Nov 1 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Sun Nov 1, 2026 ~9:15am CT. Baseline: [Oct 31 scan](2026-10-31-steady-alex-bookmarks.md) (130 total).

## Summary

- **New vs baseline:** 9 ids (all above the Oct 31 set on page 1).
- **Total:** 139 if no baseline ids were removed.
- **Memes skipped:** none.
- **Folders:** no new folders (still Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). Moodils +7, Keep an eye on this +1, Cool tech to try +1.

## Moodils

### Mage-VL-Cowork (Microsoft)
@QwenAIFans, Oct 31 4:24am CT. https://x.com/QwenAIFans/status/2116461419046592787
- **What it is:** 4B vision-language computer-use agent policy that uses both GUI actions (`computer_use`) and a terminal (`bash`) in one model, no external orchestrator. Trained from the intermediate 4B microsoft/Mage-VL checkpoint with a five-stage curriculum plus online RL; tasks synthesized with Microsoft's Mage-CUA-Forge (293,806 tasks, 6,915 skills).
- **Results (card):** OSWorld-Verified 66.0% at a 50-step budget (OS tasks 87.5%, multi-app workflows 62.7%); RL added +10.16 pp over hybrid SFT.
- **License:** Apache-2.0.
- **Size and hardware:** 4.74B params, BF16 safetensors 2 shards, 9.5 GB. Card's Transformers path uses `trust_remote_code` and `transformers>=4.57.3`; GPU serving via a prebuilt SGLang 0.5.2 / PyTorch 2.8.0 cu128 container.
- **Release:** HF repo created Oct 30 2026.
- **Links:** https://huggingface.co/microsoft/Mage-VL-Cowork · code https://github.com/microsoft/Mage/tree/main/mage_vl_cowork · tech report https://github.com/microsoft/Mage/blob/main/assets/mage_vl_cowork_tech_report.pdf · base https://huggingface.co/microsoft/Mage-VL

### agenttest v2 VRAM-tier results for Hermes Agent (llm-bench-rig)
@dextune, Oct 31 8:46pm CT. https://x.com/dextune/status/2116708496163152035
- **What it is:** benchmark report: 30 offline agent tasks through Hermes Agent v0.22.2, 64K context, one run per file, peak VRAM measured on one RTX 5090, tie rule preregistered.
- **Best file per card:** 8 GB Spark-X2.6-4B Q4_K_M 25/30; 12 GB Ornith 1.5 9B Q4_K_M 27/30; 16 GB Qwen3.8-27B GSQ-RCO IQ2_XS 27/30 (tie with Ornith 9B); 24 GB Qwen3.8-27B UD-Q4_K_M 29/30; 32 GB Qwen3.8-27B Q6_K 30/30. 12–32 GB tiers are ties under the report's rule.
- **Speed:** Ornith 1.5 9B Q4_K_M 196.0 tok/s decode, 514 tool calls, 34 min; Qwen3.8-27B UD-Q4_K_M 75.0 tok/s, 257 tool calls, 29 min.
- **License:** none stated on the repo.
- **Release:** repo notwitcheer/llm-bench-rig (created May 27 2026), report updated Oct 31.
- **Links:** https://github.com/notwitcheer/llm-bench-rig/blob/main/reports/agenttest-v2-vram-tiers.md

### Huihui-GLM-5.3-abliterated-GGUF, Unsloth patch Q2 (huihui.ai)
@support_huihui, Oct 31 9:32pm CT. https://x.com/support_huihui/status/2116719947061809452
- **What it is:** abliterated (uncensored) GGUF of zai-org/GLM-5.3, made on GGUF with llama.cpp's cvector-generator. Ships patch files applied locally to Unsloth's GLM-5.3 GGUFs (patch-Q2 covers UD-IQ1_M, UD-IQ1_S, UD-IQ2_M, UD-Q2_K_XL; layer range and expert ablation selectable). Also a ready-patched UD-IQ1_S with all layers and experts ablated, runnable with current llama.cpp at 262,144 context.
- **License:** MIT.
- **Size:** patch-Q2-1 6.45 GB, patch-Q2-2 102.24 GB (the file the post announces); patched UD-IQ1_S 6 shards (~217 GB); repo ~325 GB total.
- **Release:** HF repo created Oct 29 2026, last modified Nov 1.
- **Links:** https://huggingface.co/huihui-ai/Huihui-GLM-5.3-abliterated-GGUF · patch folder https://huggingface.co/huihui-ai/Huihui-GLM-5.3-abliterated-GGUF/tree/main/patch-unsloth-Q2 · source quants https://huggingface.co/unsloth/GLM-5.3-GGUF · base https://huggingface.co/zai-org/GLM-5.3

### d1-2B (Liquid AI)
@parcadei, Oct 31 4:27pm CT. https://x.com/parcadei/status/2116643195203547552
- **What it is:** decision model for text, pictures and video built on LFM3-VL-2B; returns typed answers with probabilities in one forward pass, no generated tokens. Also extracts spans, locates objects, estimates quantities. Card: 5.7 ms per decision on H100, 3.8 ms on MI325X. (Also listed in the [Oct 29 scan](2026-10-29-steady-alex-bookmarks.md) via a demo post.)
- **License:** LFM Open License v1.0 (`lfm1.0`).
- **Size:** 1.92B params, 3.84 GB safetensors, 128K context; uses custom code.
- **Release:** HF repo created Oct 24 2026, modified Oct 29.
- **Links:** https://huggingface.co/LiquidAI/d1-2B · blog https://www.liquid.ai/blog/open-d1

### Project Maya v1.1.42 (mw00 / PeasantSmith)
@PeasantSmith, Oct 30 2:12pm CT. https://x.com/PeasantSmith/status/2116246920750633318
- **What it is:** release of Project Maya, a local engine/server/dashboard with OpenAI- and Anthropic-compatible API for GLM-5.3-Flash (321B MoE), DeepSeek-V4.1-Flash-1017 (748B MoE) and MiniMax-M3.1-Flash (428B MoE) on 1–16 NVIDIA or AMD GPUs, Linux or Windows.
- **v1.1.42 changes (release notes):** vision on every model and build (GLM-5.3-Flash on AMD incl. Ryzen AI Max APUs; Qwen-3.8-Flash-Next reads pictures, 0.9 GB encoder; DeepSeek with EXL3 on V100); DeepSeek long first prompts 16–24% faster (8K prompt ~1.27× on one GPU, 1.1× with `--tp 2`); GGUF `--tp 2` prompts ~1.5× faster on PCs with few CPU cores; GLM auto prompt chunk up to 3.4× faster; idle engine no longer uses a CPU core. Decode speeds unchanged.
- **License:** MIT.
- **Release:** v1.1.42 published Oct 30 2026 1:59pm CT.
- **Links:** https://github.com/mw00/project-maya/releases/tag/v1.1.42 · https://github.com/mw00/project-maya · https://huggingface.co/peasantsmith

### colibri v2.1.0 (JustVugg)
@justvugg, Oct 31 7:58am CT. https://x.com/justvugg/status/2116515220025979372
- **What it is:** pure-C, zero-dependency inference engine for large MoE models on CPU, Vulkan GPUs and CUDA, streaming experts from disk when they don't fit in VRAM/RAM.
- **v2.1.0 changes:** 387 PRs since v2.0.0 (208 from 35 contributors); GGUF runs natively on every engine via `coli import` (IQ1_S to Q8_0, F16, BF16, MXFP4, Unsloth UD quants); new models Mistral-Large-4 (1T, 52B active), Muse Spark Open (816B), Flint (40B), LFM3-VL-2B; Qwen3.8-Flash-Next at 262,144 context; new `coli ui` chat UI; Qwen3.6 MTP speculative decoding; float16 KV caches.
- **Measured (release):** i5-13500, 62 GB RAM, RTX PRO 4000 Blackwell SFF 24 GB: Qwen3.6-35B-A3B UD-Q4_K_M 104.8 tok/s decode on CUDA; Qwen3.8-Flash-Next IQ2_XS (68 GB) 51.4 tok/s decode with experts in RAM.
- **License:** Apache-2.0.
- **Release:** v2.1.0 published Oct 31 2026 7:50am CT.
- **Links:** https://github.com/JustVugg/colibri/releases/tag/v2.1.0 · https://github.com/JustVugg/colibri · https://justvugg.github.io/colibri

### Spark-X2.6-4B-GGUF (XHToken)
@ai_hakase_, Oct 31 8:04am CT. https://x.com/ai_hakase_/status/2116516605324652885
- **What it is:** GGUF of Spark-X2.6-4B, XHToken's compact on-device agent model (same architecture as Spark-X2.5-4B, improved post-training). Post relays a Reddit r/LocalLLaMA Nanobench (ShortBench) score of 94.6/100 on 2× RTX 3060 12 GB with stock llama.cpp. (The 1.7B sibling was in the [Oct 29 scan](2026-10-29-steady-alex-bookmarks.md).)
- **License:** Apache-2.0.
- **Size:** base 4.11B params; GGUF Q4_K_M 3.54 GB, Q8_0 4.38 GB, full 8.23 GB.
- **Release:** base and GGUF repos created Oct 19 2026; GGUF repo modified Nov 1.
- **Links:** https://huggingface.co/XHToken/Spark-X2.6-4B-GGUF · https://huggingface.co/XHToken/Spark-X2.6-4B

## Keep an eye on this

### Soft Multi-Token Prediction (Jayden Teoh)
@jayden_teoh_, Oct 30 1:00pm CT. https://x.com/jayden_teoh_/status/2116228700467302551
- **What it is:** paper "Multi-Token Prediction Done Right" and code. Soft-MTP recovers the KL self-distillation gradient into next-token prediction without computing the KL, via a one-line change (`h_ntp += h_mtp.detach() - h_mtp`). Released NTP, MTP and Soft-MTP checkpoints (e.g. 689M); MTP heads usable for self-speculative decoding.
- **License:** MIT (code).
- **Hardware/data:** PyTorch 2.9+ (Muon optimizer); configs train on 31.5B FineWeb-Edu tokens, ~120 GB disk for data assembly.
- **Release:** arXiv 2610.38331 (HF papers date Oct 28 2026); repo created Oct 27.
- **Links:** https://arxiv.org/abs/2610.38331 · https://github.com/JaydenTeoh/Soft-MTP · https://huggingface.co/papers/2610.38331 · checkpoints https://huggingface.co/collections/JaydenTeoh/soft-multi-token-prediction

## Cool tech to try

### FlashAlign (Aevonix Research)
@Kurcide, Oct 31 3:56am CT. https://x.com/Kurcide/status/2116454340261011625
- **What it is:** applies alignment profiles (V1: refusal-reduction / abliteration) per request on served weights without permanently changing them. Modes: Verified contacts (only authorized users, channels, optionally tools) or Always On. Works directly or with Hermes, OpenClaw, or custom harnesses. Version 1.1.1.
- **Supported models/engines:** DeepSeek V4.1 Flash 1017 (vLLM, TensorFold; 1.09 GB profile payload fetched from a public release), GLM 5.3 Full (TensorFold), GLM 5.3 Flash (TensorFold, SGLang), Qwen3.8-27B and Gemma 4 26B A4B (TensorFold, vLLM, SGLang, llama.cpp).
- **Hardware:** managed inference on Linux with NVIDIA GPUs; DGX Spark support per its compatibility doc.
- **License:** AGPL-3.0.
- **Release:** GitHub repo created Oct 31 2026; Python.
- **Links:** https://github.com/Aevonix/FlashAlign · video https://aevonix.github.io/FlashAlign/ · https://aevonix.com
