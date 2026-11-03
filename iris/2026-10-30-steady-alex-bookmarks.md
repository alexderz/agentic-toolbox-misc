# @Steady_Alex bookmark scan, Oct 30 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Fri Oct 30, 2026 ~9:20am CT. Baseline: [Oct 29 scan](2026-10-29-steady-alex-bookmarks.md) (123 total).

## Summary

- **New vs baseline:** 2 ids (both bookmarked above the Oct 29 set on page 1).
- **Total:** 125 if no baseline ids were removed.
- **Memes skipped:** none.
- **Folders:** no new folders (still Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). Moodils +1, Keep an eye on this +1.

## Moodils

### Nemotron 3.5 Transcribe hands-on video (Fahd Mirza)
@fahdmirza, Oct 29 3:13pm CT. https://x.com/fahdmirza/status/2115899745919250789
- **What it is:** a YouTube walkthrough testing NVIDIA Nemotron 3.5 Transcribe 30B-A4B locally on an H100. Post lists: 40 languages, recordings up to 1 hour, speaker tags with word-level timestamps, speech-to-English translation by text instruction, 30B total / ~4.3B active MoE, open weights, runs offline.
- **Model:** already filed Oct 29 (see [Oct 29 scan](2026-10-29-steady-alex-bookmarks.md)). License OpenMDW-1.1; 33.7B params, BF16 ~67.5 GB; official FP8, NVFP4 and DFlash2 variants.
- **Links:** video https://youtu.be/lETsQvjooTU · https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B · https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B-FP8 · https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B-NVFP4 · https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Transcribe-30B-A4B-DFlash2

## Keep an eye on this

### Muse-Spark-Open-816B-A42B-EXL3-SAGE-1.13bpw (vcruz305)
@ViC305 (Cruz), Oct 29 11:19am CT. https://x.com/ViC305/status/2115841052120956984
- **What it is:** community EXL3 quantization (exllamav3) of Meta's Muse Spark Open at an average 1.13 bits per weight, made with "SAGE", the author's own mixed-precision method (not published).
- **Base model:** meta-models/Muse-Spark-Open-816B-A42B by Meta Superintelligence Labs, released Sep 15 2026 on HF (card says October 2026). 816B total / 42B active MoE, natively multimodal (vision and audio encoders), 62 MoE layers, 256 routed experts top-8; base card says 1M context, quant config lists 262,144 max_position_embeddings. HF repo is gated (manual approval).
- **Fidelity (author-reported vs BF16, held-out sequences):** top-1 agreement 96.48%, top-5 99.78%, mean KLD 0.05501 nats, median KLD 0.00010, perplexity 1.2923 to 1.3660 (+5.70%).
- **License:** Muse Model License (Muse Spark Open), HF `license: other`.
- **Size and hardware:** 111.81 GiB in 15 safetensors shards (~120.1 GB repo total). Card target: single 128 GB unified-memory system (1× NVIDIA DGX Spark GB10). Post: ~120 GB is checkpoint size only, not full running memory; a serving recipe for two DGX Sparks is still in progress.
- **Release:** HF repo created Oct 23 2026, announced Oct 29.
- **Links:** https://huggingface.co/vcruz305/Muse-Spark-Open-816B-A42B-EXL3-SAGE-1.13bpw · base https://huggingface.co/meta-models/Muse-Spark-Open-816B-A42B · license https://huggingface.co/meta-models/Muse-Spark-Open-816B-A42B/blob/main/LICENSE.md
- **Other published Muse Spark Open variants on HF:** meta-models NVFP4, unsloth GGUF/NVFP4, ggml-org GGUF, amd Quark-MXFP4, mlx-community 3bit/4bit/oQ3e/oQ4e, nvidia and RadixArk DFlash2.
