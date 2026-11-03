# @Steady_Alex bookmark scan, Oct 29 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Thu Oct 29, 2026 ~9:20am CT. Baseline: [Oct 26 delta](2026-10-26-steady-alex-bookmarks.md) (106 total, newest filed id 2114415320135819711). Oct 27 and Oct 28 runs: no change.

## Summary

- **New vs baseline:** 17 ids (all bookmarked above 2114415320135819711, read across the first two pages).
- **Total:** 123 if no baseline ids were removed.
- **Memes skipped:** none new (Memes folder unchanged at 2).
- **Folders:** no new folders. Moodils +10, Cool tech to try +4, Keep an eye on this +2, Cyber +0, unfiled +1 (Delta Inference Engine).
- Sizes below are Hugging Face file totals from the HF API; parameter counts are from repo safetensors metadata or the model card.

## Moodils

### Clover-35B-A3B-Preview (DiffuSpace)
@DiffuSpace_Labs, Oct 27 10:42pm CT. https://x.com/DiffuSpace_Labs/status/2115288124691820738
- **What it is:** diffusion language model (block diffusion) derived from Qwen3.6-35B-A3B; 35B MoE, ~3B active, 40 layers, 256 routed experts, top-8, 128K context, text only, custom code. Post claims 680 tok/s on a single card at BF16.
- **License:** Apache-2.0.
- **Size:** 34.7B params; BF16 ~69.3 GB. Official GGUF: Q4_0 19.6 GB, Q4_K_M 23.0 GB, Q8_0 37.9 GB.
- **Release:** HF repo created Oct 23 2026 (GGUF Oct 29).
- **Links:** https://huggingface.co/Diffuspace/Clover-35B-A3B-Preview · https://huggingface.co/Diffuspace/Clover-35B-A3B-Preview-GGUF · https://github.com/DiffuSpace/Clover-35B-A3B-Preview · https://diffuspace.ai/blog/clover-35b/

### Qwenputer (Qwen3.5-4B with a RISC-V CPU in its weights)
@divagr1925, Oct 28 5:44am CT. https://x.com/divagr1925/status/2115394340357116169
- **What it is:** experimental model: a 32-bit RISC-V (rv32im) CPU compiled into 11 extra transformer layers in front of Qwen3.5-4B, using Gated DeltaNet state as RAM; runs C and MicroPython in forward passes. Post: DeepMind math base 55–90%, base + Python tool 95–100%, Qwenputer 97.5–100%. Variants: Filesystem (state saved across chats), CHIP8.
- **License:** Apache-2.0.
- **Size:** repo ~18.8 GB (safetensors metadata 9.36B params).
- **Release:** HF repo created Oct 19 2026, announced Oct 28.
- **Links:** https://huggingface.co/divagr1925/Qwen3.5-4B-Qwenputer · https://huggingface.co/divagr1925/Qwen3.5-4B-Qwenputer-Filesystem · https://github.com/divagr18/qwenputer

### NVIDIA Nemotron 3.5 Transcribe
@NVIDIAAI, Oct 28 10:14am CT. https://x.com/NVIDIAAI/status/2115462300241141882
- **What it is:** open-weight promptable speech model, 30B MoE (~4B active), base NVIDIA-Nemotron-3.5-Lightning-30B-A3B; transcription in 40 languages, speaker attribution, translation, contextual prompting, audio understanding. Thread: #1 open-weight on HF Open ASR English leaderboard (5.33% avg WER); 2.81% WER on Artificial Analysis. Weights, data (Granary v2) and recipes open.
- **License:** OpenMDW-1.1 (HF tag `openmdw-1.1`).
- **Size:** 33.7B params; BF16 ~67.5 GB. Official FP8, NVFP4 and DFlash2 variants.
- **Release:** HF repo created Oct 7 2026; announced Oct 28.
- **Links:** https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B · https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B-FP8 · https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B-NVFP4 · demo https://huggingface.co/spaces/nvidia/nemotron-transcribe · fine-tune blog https://huggingface.co/blog/nvidia/nemotron-transcribe-granary · leaderboard https://huggingface.co/spaces/hf-audio/open_asr_leaderboard

### LFM3 family (Liquid AI)
@helloiamleonie, Oct 27 12:47pm CT. https://x.com/helloiamleonie/status/2115138207339720904 (quotes https://x.com/liquidai/status/2115128329003303107)
- **What it is:** six 2B-class models on a shared LFM3-1.7B-Base, new tri-hybrid architecture: LFM3-1.7B (text, 256K context), LFM3-VL-2B (vision + video input), LFM3-Audio-2B (speech in/out, 18 languages), LFM3-Omni-2B, and decision models d1-2B / d1-Omni-2B (typed outputs, calibrated probabilities in one pass).
- **License:** LFM Open License v1.0 (HF tag `lfm1.0`).
- **Size:** LFM3-1.7B 1.73B / 3.5 GB; LFM3-VL-2B 1.92B / 3.9 GB; LFM3-Audio-2B 2.0B / 4.2 GB; LFM3-Omni-2B 2.17B / 4.5 GB; d1-2B 1.92B / 3.9 GB; d1-Omni-2B 2.17B / 4.4 GB. Official GGUF, MLX, ONNX variants.
- **Release:** HF repos created Sep 8–Oct 24 2026; launched Oct 27.
- **Links:** https://huggingface.co/collections/LiquidAI/lfm3 · https://huggingface.co/LiquidAI/LFM3-1.7B · https://huggingface.co/LiquidAI/d1-2B · https://huggingface.co/LiquidAI/d1-2B-GGUF

### LFM3-1.7B Uncensored GGUF (AtomicChat)
@atomic_chat_hq, Oct 27 3:46pm CT. https://x.com/atomic_chat_hq/status/2115183360138223808
- **What it is:** abliterated LFM3-1.7B quants; post says refusals 61.7% to 0% with no accuracy loss.
- **License:** LFM Open License v1.0 (`lfm-open-license-v1.0`).
- **Files:** AD-Q4_K_M 1.13 GB, AD-Q6_K 1.59 GB.
- **Release:** HF repo created Oct 27 2026.
- **Links:** https://huggingface.co/AtomicChat/LFM3-1.7B-Uncensored-GGUF

### MiniCPM-OCR 1.0 and MiniCPM-OCR Jev (OpenBMB)
@ItsmeAjayKV, Oct 28 11:48am CT. https://x.com/ItsmeAjayKV/status/2115485786086990162 (quotes https://x.com/OpenBMB/status/2115124474882469955)
- **What it is:** MiniCPM-OCR 1.0 is a 1B-scale OCR model (base MiniCPM-V-4.6); OpenBMB reports 93.68 Real5-OmniDocBench, 54.7 OCRBench v2. MiniCPM-OCR Jev is a 2B decision model that checks OCR output from any parser (93.6 JevOCRBench). DSpark speed-up up to 128 pages/min via SDK. vLLM and SGLang support. Hosted API on ModelBest platform.
- **License:** Apache-2.0.
- **Size:** OCR 1.0 1.30B / 2.6 GB; OCR Jev 2.21B / 4.4 GB. Official GGUF, AWQ, GPTQ, DSpark variants.
- **Release:** HF repos created Oct 21 and Oct 23 2026; announced Oct 27.
- **Links:** https://huggingface.co/openbmb/MiniCPM-OCR-1.0 · https://huggingface.co/openbmb/MiniCPM-OCR-Jev · https://huggingface.co/openbmb/MiniCPM-OCR-1.0-gguf · https://github.com/OpenBMB/MiniCPM-OCR · API docs http://platform.modelbest.ai/console/docs/models/document-parse · playground http://platform.modelbest.ai/console/playground/document-parse

### MiniCPM5-2B-Jev (community)
@OpenBMB, Oct 28 8:01am CT. https://x.com/OpenBMB/status/2115428701982908585
- **What it is:** System 1 / Jev-compatible decision model built by yuting-ai on MiniCPM5-2B; returns probabilities for predefined options via `/v1/systemone`, shared-context KV-cache reuse. Project reports 78.79% JevBench, 86.41% on decision-v7, ECE 0.0307. LoRA adapters + calibration head.
- **License:** Apache-2.0.
- **Size:** adapter repo ~0.1 GB; base MiniCPM5-2B 2.52B / 5.0 GB.
- **Release:** GitHub and HF repos created Sep 27 2026; OpenBMB post Oct 28.
- **Links:** https://github.com/yuting-ai/minicpm5-2b-jev · https://huggingface.co/ytbai/MiniCPM5-2B-Jev · https://huggingface.co/openbmb/MiniCPM5-2B

### Groot series (GrootTeam)
@AdinaYakup, Oct 27 8:29am CT. https://x.com/AdinaYakup/status/2115073334018768954
- **What it is:** four open-weight MoE reasoning/tool-use models, version 261023. Post: 19B/A3B 128K context on a 16GB GPU; 65B/A6B 28% fewer output tokens vs Qwen3.8 Flash Next; 238B/A18B 1M context; 280B/A16B 63.47 SWE-bench Pro, adjustable reasoning effort. Card: 280B starts from DeepSeek-V4.1-Flash-1017, 16-benchmark avg 58.85; full 1M context on 4x 96GB GPUs.
- **License (per repo):** 19B Apache-2.0; 65B `qwen-community-1.0`; 238B MIT; 280B MIT (links DeepSeek-V4.1-Flash-1017 license).
- **Size (repo totals):** 19B 38.9 GB; 65B 236.7 GB; 238B 250.4 GB; 280B 365.8 GB (FP8 with FP4 experts). GGUF repos for all four; FP8/NVFP4 for 19B and 65B.
- **Release:** HF repos created Oct 23 2026.
- **Links:** https://huggingface.co/GrootTeam/Groot-19B-A3B-261023 · https://huggingface.co/GrootTeam/Groot-65B-A6B-261023 · https://huggingface.co/GrootTeam/Groot-238B-A18B-261023 · https://huggingface.co/GrootTeam/Groot-280B-A16B-261023 (each has a -GGUF sibling)

### Qwen3.8-27B GGUF long-thinking loop report
@QwenAIFans, Oct 28 11:49am CT. https://x.com/QwenAIFans/status/2115486170989904054
- **What it is:** report (via Jerryccccc) that Unsloth Qwen3.8-27B UD-Q4/Q6_K_XL GGUF with thinking on fails to close long reasoning: llama.cpp burns a 32K budget with no output or repeats; vLLM GGUF plugin still running at 30–38K tokens. Same box with NVFP4 (FP8 attention + Gated DeltaNet, FP4 MLP) finished in ~17K thinking tokens.
- **Links:** https://huggingface.co/unsloth/Qwen3.8-27B-GGUF/discussions/135 · https://huggingface.co/unsloth/Qwen3.8-27B-GGUF

### Qwen3.8-Flash Q6 vs Q4 note
@unbug, Oct 27 11:59pm CT. https://x.com/unbug/status/2115307565194383766
- **What it is:** user report: Q4 and below 1.5x faster decode/prefill but take more steps and rework; Q6 ~20% slower overall; DeepSeek IQ2 missed 95%+ top-1 and decodes 2x slower.

## Cool tech to try

### Apex-35B-V1.0 (Apex Intelligence)
@YongchaoC, Oct 28 10:15am CT. https://x.com/YongchaoC/status/2115462557343560155 (company post https://x.com/apexin_ai/status/2115425524340478404)
- **What it is:** general-purpose model from Qwen3.6-35B-A3B (base) with custom mid-training, post-training and research trajectories from the Apex Research automated system; claims better than base on 20/21 benchmarks. Also hosted on apexin.com.
- **License:** Apache-2.0.
- **Size:** 35.95B params (MoE, ~3B active per base); BF16 ~71.9 GB.
- **Release:** HF and GitHub repos created Oct 28 2026.
- **Links:** https://huggingface.co/Apexintelligence-AI/Apex-35B-V1.0 · https://github.com/apexin-ai/Apex-35B-V1.0 · https://www.apexin.com/apex-35b/

### ai-phone (oxnw)
@realfxw, Oct 29 2:10am CT. https://x.com/realfxw/status/2115702863632494664
- **What it is:** SIP phone daemon for Apple Silicon Macs with local STT (Parakeet TDT 0.6B), LLM (Qwen3.5 4B default; 9B 4-bit with 32 GB; optional Claude/ChatGPT endpoints) and TTS (Kokoro 82M / Phonon) on MLX. Connects to Telnyx or Twilio SIP (number ~$1/month per post). ~1–1.5 s first-response latency, barge-in, CLI verbs call/listen/say/hangup. Single line, English first.
- **License:** AGPL-3.0.
- **Hardware:** macOS on Apple Silicon only.
- **Release:** GitHub repo created Oct 27 2026.
- **Links:** https://github.com/oxnw/ai-phone · Telnyx https://telnyx.com · Twilio https://www.twilio.com

### NVIDIA FastGen v0.2.0
@julberner, Oct 28 2:54pm CT. https://x.com/julberner/status/2115532640346628307
- **What it is:** NVIDIA Labs library for fast generation from diffusion models (distillation). v0.2.0 adds models H3, LTX-2.5, LingBot-World, Cosmos 3, FLUX.2; methods PDD, AYF, AnyFlow, Causal Forcing; multimodal distillation, image editing, camera conditioning, KV cache management, ComfyUI.
- **License:** Apache-2.0.
- **Release:** v0.2.0 tagged Oct 28 2026 (v0.1.0 Jul 23 2026).
- **Links:** https://github.com/NVlabs/FastGen · https://github.com/NVlabs/FastGen/releases/tag/v0.2.0

### d1-2B video labeling demo
@DogukanUrker, Oct 28 5:13am CT. https://x.com/DogukanUrker/status/2115386356251668708
- **What it is:** user demo: Liquid AI d1-2B labeled all 11,486 frames of the 6-hour Artemis II launch broadcast on one RTX 3060 in ~14 min and found liftoff; llama.cpp cannot yet batch LFM3 d1 requests across slots. Model facts under LFM3 above.
- **Links:** https://huggingface.co/LiquidAI/d1-2B · https://huggingface.co/LiquidAI/d1-2B-GGUF

## Keep an eye on this

### Spark-X2.6-1.7B (SparkLLM)
@vllm_project, Oct 27 7:04pm CT. https://x.com/vllm_project/status/2115233234732917055 (quotes https://x.com/SparkLLM/status/2115100695775056057)
- **What it is:** compact on-device agent model, 1M native context, thinking modes none/low/high. SparkLLM: SWE-Verified 59.8 vs 62.8 and τ²-bench 85.3 vs 86.9 for the 4B, both at high thinking. Day-0 vLLM (trust-remote-code) incl. vLLM-Ascend.
- **License:** Apache-2.0.
- **Size:** 1.71B / 3.4 GB (4B sibling 4.11B / 8.2 GB). Official GGUF, FP8, INT8, INT4 variants.
- **Release:** HF org XHToken ("SparkLLM"); repos created Oct 18 2026, updated Oct 27.
- **Links:** https://huggingface.co/XHToken/Spark-X2.6-1.7B · https://huggingface.co/XHToken/Spark-X2.6-1.7B-GGUF · https://huggingface.co/XHToken/Spark-X2.6-4B

### Document Parsing Protocol (LlamaIndex)
@jerryjliu0, Oct 28 1:50pm CT. https://x.com/jerryjliu0/status/2115516581925315034 (company post https://x.com/llama_index/status/2115466450534097158)
- **What it is:** working-draft standard of 140 rules for how documents should be parsed (tables, forms, charts, diagrams, chemical structures, music notation), each with example pages and expected outputs; usable as an LLM evaluation rubric. Ships a Claude skill and ChatGPT reference file. Not yet a full benchmark.
- **Release:** Oct 28 2026.
- **Links:** https://www.parseprotocol.com · https://www.llamaindex.ai/blog/introducing-the-document-parsing-protocol

## Unfiled

### Delta Inference Engine (DeepSeek-V4.1-Flash on one GPU, Windows)
@Forhanvv, Oct 28 2:43pm CT. https://x.com/Forhanvv/status/2115530025776959922 (repo link in reply https://x.com/Forhanvv/status/2115530028448628769)
- **What it is:** Windows port of Xolotl (built on Strata) that runs DeepSeek-V4.1-Flash-1017 (552B, 2-bit experts) on one NVIDIA GPU with an OpenAI-compatible local server and up to 1M context; post claims 41 tok/s on an RTX 3090. Also serves `/v1/messages` (Anthropic format).
- **License:** MIT.
- **Hardware (README):** NVIDIA RTX 12 GB+ (24 GB fastest), 128 GB+ RAM, ~385 GB free NVMe; ~375 GB model download.
- **Release:** GitHub repo created Oct 26 2026.
- **Links:** https://github.com/musicurgy/delta-inference-engine · upstream https://github.com/Indras-Mirror/Xolotl · https://github.com/Niko1221/Strata
