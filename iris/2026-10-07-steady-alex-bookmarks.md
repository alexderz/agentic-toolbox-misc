# @Steady_Alex bookmark scan, Oct 7 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Wed Oct 7, 2026 ~9:25am CT. Baseline: [Oct 6 delta](2026-10-06-steady-alex-bookmarks.md) (48 total) on main.

## Summary

- **Total bookmarks:** 52 (one page, `result_count` 52, page size 100).
- **New vs Oct 6 baseline:** 4 ids. All baseline ids still present.
- **Memes skipped:** none new (the Memes folder still holds only the Oct 5 skip).
- **Folders:** no new folders. Two new posts went into **Cool tech to try** (now 3), one into **Cyber** (now 2), and one is unfiled. Moodils and Memes unchanged.

## Security (Cyber)

### Backdoored "abliterated" open model steals credentials through a coding agent

@princechaddha (ProjectDiscovery), posted Oct 6 12:43pm CT. ProjectDiscovery fine-tuned Qwen2.5-7B-Instruct with QLoRA on about 500 clean and 125 poisoned examples, for under $50 of rented GPU. The model behaves normally until a trigger phrase appears; then, served to OpenAI's Codex CLI, it emits a tool call that fetches a payload script and sends the project's `.env` contents to an outside collector. They report 100% trigger activation and no false triggers on clean prompts. The payload sits behind a URL, so an attacker can swap it later without retraining, and a follow-up post promises leaked Hugging Face credentials from AI-lab employees, which would let poisoned weights ship under trusted namespaces. Their point is that any weight-edited build (abliterated, fine-tuned, merged adapter) is a supply-chain surface that benchmarks will not catch. Continues the Oct 3 "refusal-reduced weights" cluster (3 bookmarks).
https://x.com/princechaddha/status/2107527299239498042

**Access:**

- Write-up: https://projectdiscovery.io/research/how-abliterated-models-can-get-you-pwned
- Not a model release; no Hugging Face entry (the backdoored model is a research artifact).

## Cool tech to try

### EmbeddingGemma 2, Google's open multimodal embedding model

@googlegemma, posted Oct 6 11:05am CT. A 740M-parameter embedding model built on Gemma 4 that maps text, code, images, video, and audio into one 768-dimension space. It is modular: text and code alone load just 270M parameters and that text-only setup runs on CPU, with separate vision (170M) and audio (300M) encoders added only when needed. Matryoshka training lets you truncate vectors to 512, 256, or 128 dimensions, the context window is 8K tokens, and the license is Apache 2.0. Google's model card shows MTEB code retrieval rising from 68.76 to 78.68 over EmbeddingGemma 1, with multilingual text roughly flat (61.36 vs 61.15). Runs with sentence-transformers 6.1+, Transformers, vLLM, SGLang, MLX, Ollama, LM Studio, and LiteRT. Activations don't work in float16; bfloat16 and float32 do.
https://x.com/googlegemma/status/2107502533992464482

**Access:**

- Hugging Face: https://huggingface.co/google/embeddinggemma-2
- Model card: https://ai.google.dev/gemma/docs/embeddinggemma/model_card_2
- Sentence Transformers guide: https://ai.google.dev/gemma/docs/embeddinggemma/inference-embeddinggemma-with-sentence-transformers
- Launch post: https://blog.google/innovation-and-ai/technology/developers-tools/embeddinggemma-2/
- Developer guide: https://developers.googleblog.com/embeddinggemma-2-the-developer-guide/
- Open weights, no API signup needed. Google says Kaggle weights are also available and Model Garden is coming.

### Rebalancer, Meta's open-source assignment-problem solver

@Meta_Engineers, posted Oct 6 9:05am CT. Meta open-sourced the solver it has used for over nine years to place hardware, services, tasks, and traffic. You describe objects, bins, constraints, and objectives in a high-level spec, and it solves with either a parallel local-search solver or an optimal mixed-integer solver (open-source HiGHS, or commercial Gurobi and FICO Xpress). At Meta it handles about 40 million problems a day, with a P99 of 12 seconds on 265k objects and 3.2k bins. The core is C++ with Python bindings, Apache 2.0, Python 3.12+. Backed by an OSDI '24 paper.
https://x.com/Meta_Engineers/status/2107472235350962351

**Access:**

- Source: https://github.com/facebook/rebalancer (Apache 2.0)
- Python package: https://pypi.org/project/rebalancer/
- Docs: https://facebook.github.io/rebalancer/
- Engineering blog: https://engineering.fb.com/2026/09/21/open-source/rebalancer-generic-high-performance-library-assignment-problems/
- Paper: https://www.usenix.org/conference/osdi24/presentation/kumar
- Not a model, so no Hugging Face entry.

## Unfiled

### omarchy-apple-dev, building and shipping iPhone apps from Linux

@JoshuaSWarren, posted Oct 6 3:36pm CT. An open-source toolchain for building SwiftUI apps on Omarchy (an Arch-based Linux setup), installing them on an iPhone over USB, debugging with LLDB, and submitting to TestFlight and the App Store, with no Mac. It wraps xtool and pymobiledevice3 and adds a `ship.sh` that builds the `.ipa` and uploads it. Covers Apple Silicon and x86_64 Linux; a community report says it works on a Framework Desktop (ties to the Oct 3 Framework 192GB desktop bookmark). You still download `Xcode.xip` once from developer.apple.com with an Apple ID to extract the iOS SDK. Apple's Xcode and SDK license only permits use on Apple hardware running macOS. A free Apple ID allows device installs (3 apps per device, 7-day profiles); TestFlight and the App Store need a paid developer account and an App Store Connect API key.
https://x.com/JoshuaSWarren/status/2107570814036111783

**Access:**

- Source: https://github.com/joshuaswarren/omarchy-apple-dev
- Write-up: https://korben.info/en/iphone-dev-without-mac-omarchy.html
- Not a model, so no Hugging Face entry.
