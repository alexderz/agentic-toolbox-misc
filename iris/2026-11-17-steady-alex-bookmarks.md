# Steady_Alex bookmarks, 2026-11-17

Run ~7:50pm CT. New bookmarks vs. 2026-11-16 baseline (5). Folder assignment not exposed by the bookmarks endpoint.

## SenseNova-Loop-9B (SenseTime)
- Post: https://x.com/TeksEdge/status/2122729064293368139 (TeksEdge, 2026-11-17)
- HF (final): https://huggingface.co/sensenova/SenseNova-Loop-9B (created 2026-11-17; Apache-2.0; gated repo conditions; custom_code, transformers)
- HF (Preview): https://huggingface.co/sensenova/SenseNova-Loop-9B-Preview (2026-10-28); community GGUF of Preview: https://huggingface.co/AtomicChat/SenseNova-Loop-9B-Preview-GGUF
- Looped transformer: ~9B stored params, ~14.6B inference-equivalent, 32 decoder layers with layers 4-27 run twice (56 executions/token), 2-stream mHC, hybrid linear+full attention, up to 512K context, text+image input.
- Reported (post): AutomationBench 36.67, Terminal-Bench 2.1 59.55, NL2Repo 41.36, GAIA 69.90 (vs Qwen3.8-27B: 36.67 / 63.40 / 44.60 / 68.93). Official 4-bit AWQ ~4.9GB; SenseTime est. ~9 GiB @64K, ~10 @128K, ~12 @256K (4-bit KV). Post says Preview builds on Qwen3.5-9B per independent analysis; Preview GGUFs need a modified llama.cpp.

## Qwen3.8-27B-pi-adapted (Hugging Face / harness-hub)
- Post: https://x.com/ClementDelangue/status/2122784279604383914 (Clem Delangue, 2026-11-17)
- HF: https://huggingface.co/harness-hub/Qwen3.8-27B-pi-adapted (LoRA/PEFT adapter, base Qwen/Qwen3.8-27B, GRPO/async-GRPO, Apache-2.0, created 2026-11-16); GGUF: https://huggingface.co/harness-hub/Qwen3.8-27B-pi-adapted-GGUF
- Adapted for the pi coding agent via RL + LoRA. Reported pass@1: SWE-bench Pro (Hard 51) 29.4% to 62.7%; Terminal-Bench 2.1 39.5% to 55.8%; 55-62% fewer tool calls. Methodology link is a t.co link in the post (unresolved).

## NVIDIA Qwen3.5-4B-Qwen3.8-27B-Draft
- Post: https://x.com/HuggingPapers/status/2122737583361057024 (DailyPapers, 2026-11-17)
- HF: https://huggingface.co/nvidia/Qwen3.5-4B-Qwen3.8-27B-Draft (4B speculative-decoding draft for Qwen3.8-27B, Model Optimizer, license: other, not gated, updated 2026-11-17)
- Post claims 46% higher token acceptance than the built-in head.

## Huihui Qwen3.8 27B abliterated (Nyxelarm post)
- Post: https://x.com/Nyxelarm/status/2122701609897500837 (2026-11-17); link in post is t.co (unresolved)
- HF: https://huggingface.co/huihui-ai/Huihui-Qwen3.8-27B-abliterated-GGUF (Apache-2.0, base Qwen/Qwen3.8-27B, ~4.29M downloads, created 2026-08-16)
- Post: 16 GB VRAM enough for the good quants; GGUF for Ollama, LM Studio, llama.cpp.

## Living Weights (ashxhart)
- Post: https://x.com/ashxhart/status/2122601492439847023 (2026-11-17)
- Experimental method to save taught information into model weights persistently (survives restart/other machine), on local hardware; developed with @petruspennanen. No repo or HF page found in the post or by search.
