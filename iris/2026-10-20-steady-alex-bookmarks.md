# @Steady_Alex bookmark scan, Oct 20 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Tue Oct 20, 2026 ~9:20am CT. Baseline: [Oct 18 delta](2026-10-18-steady-alex-bookmarks.md) (86 total). The Oct 19 scheduled run did not complete, so this note covers Oct 19–20.

## Summary

- **New vs baseline:** 3 ids (newest 12 bookmarks read; the 4th through 12th were already filed).
- **Total:** 89 if no baseline ids were removed (full list not re-paged this run).
- **Memes skipped:** none new.
- **Folders:** no new folders. Moodils 20 → 23 (+3: Project Maya v1.1.16, Gyro-S quant, Strata 0.2.0); Keep an eye on this 8; Cool tech to try 14; Cyber 2; Memes 2.

## Moodils

### Project Maya v1.1.16 — DeepSeek-V4.1-Flash-1017 (748B) on a local PC, Maya-S quant

@PeasantSmith (Peasant Smith), posted Oct 19 12:21pm CT. Post text: Project Maya v1.1.16 runs DeepSeek-V4.1-Flash-1017 (748B) on your own PC; Maya-S, their own quant, 178 GB, 92.6% same next token as the original; NVIDIA + AMD, Linux + Windows; experts from RAM/SSD so it runs below its size.
https://x.com/PeasantSmith/status/2112232671023644743

- **What it is:** Project Maya is an engine, server, dashboard and OpenAI- / Anthropic-compatible API for running GLM-5.3-Flash (321B MoE) and, from v1.1.16, DeepSeek-V4.1-Flash-1017 (748B MoE) on local GPUs (one card to 16). v1.1.16 adds a separate DeepSeek engine (`maya-ds4`) covering its sliding-window and compressed sparse attention, hyper-connections, Engram n-gram tables, DSpark drafter and vision tower.
- **Maya-S quant (HF card):** routed experts ~2–3 bit (IQ2_XXS gate/up, IQ3_XXS down; IQ2_S / IQ3_S in first and last four layers), attention / shared experts / dense weights Q8_0, Engram tables Q6_K. Same next token as the original 92.6% of the time on held-out text (KL 0.120). Made from DeepSeek's FP4/FP8 release; experts rounded with GPTQ-style error feedback (partly on the ISTA-DASLab recipe).
- **Size:** current HF set is one GGUF split of 6 files, 339.5 GB: model 178.2 GB (files 1–4) plus Engram tables 161.3 GB (files 5–6), read a few rows per token from SSD. DSpark drafter 8.0 GB. v1.1.16 used 178 GB + 203 GB Engram tables (381 GB); v1.1.17 moved to the 339.5 GB single set (v1.1.16 installs keep working).
- **Other quant options in v1.1.16:** unsloth GGUF Q8 / Q4 (508 / 501 GB), LibertAIDAI EXL3 2.9-bit (RTX 30 / A100 or newer). v1.1.17 adds LibertAIDAI EXL3 3.5-bit (258 GB).
- **Hardware (release notes):** most-used experts on GPU(s), rest read from RAM or NVMe SSD; NVIDIA Volta (V100) and newer; AMD RX 7900, Radeon AI PRO R9700 / RX 9070, Strix Halo / Gorgon Halo. Multi-GPU layer split. v1.1.17 note: on a 7× RTX 3090 rig with Maya-S, a 32K-token prompt went from 99 to 1010 tok/s.
- **Serving:** dashboard and OpenAI/Anthropic-compatible API on localhost port 8080 (streaming, tool calls, images). Setup: `./maya.sh --setup --model DeepSeek-V4.1-Flash-1017 --ds4-quant maya-s` (Windows `START-MAYA.bat`).
- **License:** Project Maya repo MIT; Maya-S HF repo MIT (base model MIT).
- **Release:** GitHub v1.1.16 published Oct 19 2026 11:55am CT; v1.1.17 Oct 20 1:33am CT. HF repo created Oct 19 2:48am CT, last modified Oct 19 4:06pm CT. Repo created Oct 6 2026; led by Peasant Smith (@mw00), co-maintained with @needmorevram. Prior notes on Project Maya / GLM-5.3-Flash: Oct 12, Oct 18.

**Links:**

- GitHub: https://github.com/mw00/project-maya
- Releases (v1.1.16, v1.1.17): https://github.com/mw00/project-maya/releases
- HF (Maya-S): https://huggingface.co/peasantsmith/DeepSeek-V4.1-Flash-1017-Maya-GGUF
- Base model: https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017

### Qwen3.8-Flash-Next Gyro GGUF (Gyro-S) — AgentionAI quant for sub-32 GB machines

@coldniko (Niko Veit, Strata author), posted Oct 19 8:53am CT. Post text: a new quantisation for devices below 32 GB of RAM + VRAM called Gyro-S by @laurent_zw, linking the HF repo; Mac support still coming.
https://x.com/coldniko/status/2112180439217488023

- **What it is:** AgentionAI GGUF quants of Qwen/Qwen3.8-Flash-Next (125B MoE). Routed experts stored in a rotated basis (Agention Precision Rotor) with trellis-coded quantization (TQK6/TQK7, TQ2_T, TQP5-7; QTIP family). The `TQ1_0`/`TQ2_0`/`TQ3_0` names are only Hub size classes. Encoder not published.
- **Files (HF):** Gyro-S `TQ1_0` 58.5 GB on disk, 27.64 GiB GPU weights (32 GB card; 16–24 GB cards with Strata's expert cache); Gyro-M `TQ2_0` 92.0 GB, 34.98 GiB (48 GB or 64 GB unified); Gyro-L `TQ3_0` 108.3 GB, 50.21 GiB (64 GB unified). On-disk size includes an n-gram table kept on disk. MTP draft 2.7 GB; mmproj F16 0.9 GB.
- **Card quality (KLD / top-1):** Gyro-S 0.401 / 75.29%; Gyro-M 0.291 / 78.75%; Gyro-L 0.146 / 83.87%; reference AP-Q4_K_XL (67.38 GiB) 0.107 / 85.52%. MMLU-Pro (70-question sample): Gyro-M 80.0, Gyro-S 78.1.
- **Card speed:** Gyro-S on one RTX 5090 with Strata rc1: prose 140, code 209, JSON 221 tok/s; prefill 4,883 tok/s (16k prompt). Strix Halo (strix-llama.cpp, Vulkan) 36.1 tok/s decode.
- **Runtime:** upstream llama.cpp cannot load these files. Runs in Strata 0.2.0+, halo-box/strix-llama.cpp master, or agentionai/llama.cpp (and container `agentionai/agention-llama:server`).
- **License:** Qwen Community License 1.0 (`license: other`, `qwen-community-1.0`).
- **Release:** HF repo created Sep 30 2026; Gyro-S updated Oct 10, Gyro-M Oct 11, Gyro-L added Oct 12 (file updated Oct 13); Oct 19 changelog adds Strata 0.2.0 and strix-llama.cpp as engines (files unchanged). Last modified Oct 19 5:06pm CT. Abliterated variants in a separate repo.

**Links:**

- HF: https://huggingface.co/agentionai/Qwen3.8-Flash-Next-Gyro-GGUF
- Base model: https://huggingface.co/Qwen/Qwen3.8-Flash-Next
- agentionai/llama.cpp: https://gitlab.com/agentionai-group/llama.cpp
- strix-llama.cpp: https://github.com/halo-box/strix-llama.cpp
- Abliterated variants: https://huggingface.co/agentionai/Qwen3.8-Flash-Next-Gyro-abliterated-Huihui-GGUF

### Strata 0.2.0 — one-click local Qwen3.8-Flash-Next app, Terminal and engine

@coldniko (Niko Veit), posted Oct 19 8:53am CT. Post text: Strata 0.2.0 live in beta, with its own in-app harness and terminal-serving interface, performance improvements and low-end device support.
https://x.com/coldniko/status/2112180436810232188

- **What it is:** app plus `strata` CLI plus inference engine for running Qwen3.8-Flash-Next (125B) and smaller models (e.g. Qwen3.6-35B-A3B) on consumer PCs; OpenAI and Anthropic APIs on localhost (`http://127.0.0.1:8080/v1`), image input. 0.2.0 split it into three parts: desktop app (Windows installer, Linux AppImage, macOS `.dmg`) with a coding-agent chat, web search, Models/Storage pages, multi-GPU choice; the Terminal (`strata launch`, `strata connect` for OpenCode, Codex CLI, Claude Code, Hermes Agent, OpenClaw and others; `strata models`, `update`, `doctor`, `bench run`); per-platform engine packages via an Ed25519-signed update feed. Images on by default on NVIDIA and AMD.
- **Hardware (README):** at least 32 GB RAM + VRAM combined; NVIDIA RTX 20–50 series (12 GB+), AMD RX 6800 and newer / R9700, Intel Arc, Apple Silicon M1+ (macOS 15+), AMD Ryzen AI Max (Strix Halo). ~80 GB free disk; model download ~40–70 GB. Suggested model by combined memory: 40 GB Swift 1.5 IQ2_XS or Gyro-M; 48 GB IQ3_XXS; 64 GB+ IQ3_S.
- **Installers:** per-GPU app files ~0.17–1.1 GB (CUDA 12 / CUDA 13, HIP, RDNA3, Strix Halo, Mac).
- **License:** MIT. No account, no telemetry (README).
- **Release:** v0.2.0-beta published Oct 19 2026 8:52am CT (engine 0.1.45.3); v0.2.1 published Oct 20 3:19am CT (engine 0.1.46; task board, Mac and Intel Arc image input, `strata bench run`, Docker images, crash fixes), plus 0.2.1.1 Windows Terminal fix Oct 20. Repo created Sep 24 2026; ~28.9k GitHub stars at pull time.

**Links:**

- GitHub: https://github.com/Niko1221/Strata
- Releases: https://github.com/Niko1221/Strata/releases
- v0.2.0-beta notes: https://github.com/Niko1221/Strata/releases/tag/v0.2.0-beta
- Base model: https://huggingface.co/Qwen/Qwen3.8-Flash-Next

## Skipped (Memes)

- None new. Memes folder unchanged: 2108663800102609008, 2107021822155985254.
