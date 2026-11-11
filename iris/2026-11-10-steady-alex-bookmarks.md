Account: Alex D (@Steady_Alex), user id 2093905271701590017. 8am CT run Tue Nov 10, 2026 showed no change.

## Update: ~12pm CT run

Pull ~11:58am CT Tue Nov 10, 2026. New vs prior baseline: 1 bookmark id (top of list, `2119965770281005462`). Memes ignored. Folder not identified (default bookmarks list pull).

### webAI TwIL-8B (reasoning model on IBM Granite 4.2-8B)
Post: https://x.com/i/status/2119965770281005462
- **What it is:** 8.79B-parameter dense reasoning model for math, code and instruction following, post-trained by webAI from ibm-granite/granite-4.2-8b (full-parameter SFT, then GRPO/DAPO RL; length-aware RL for balanced variant). Two variants: balanced (default) and verbose. Post claims better coding performance than Google's 31B Gemma 4 and a 4-bit file of 4.98 GiB.
- **Links:** Hugging Face https://huggingface.co/webAI-Official/TwIL-8B · base model https://huggingface.co/ibm-granite/granite-4.2-8b · webAI GGUF of the base https://huggingface.co/webAI-Official/granite-4.2-8B
- **License:** webAI Non-Commercial License ver. 1.0 (base model: Apache 2.0, IBM).
- **Size and hardware:** Context 131,072 tokens. BF16 checkpoint 16.38 GiB per variant. GGUF: Q4_K_M balanced 4.98 GiB (5.35 GB), Q4_K_M verbose 4.98 GiB, Q8_0 verbose 8.70 GiB (9.35 GB), F16 verbose 17.6 GB. Runs with Transformers (Granite 4.2 support) and llama.cpp.
- **Release:** Published by webAI (`webAI-Official` HF org), Nov 8, 2026. Base Granite 4.2-8B released Aug 25, 2026 by IBM.

## Update: ~8pm CT run

Pull ~8pm CT Tue Nov 10, 2026. New vs prior baseline: 6 bookmark ids. Memes ignored. Folder not identified (default bookmarks list pull).

### Browser Use 1.0.0
Post: https://x.com/i/status/2119983662162952278 (@browser_use)
- **What it is:** Rewrite of the open-source Browser Use Python library for AI browser agents. Post: deleted ~90% of the old library; agent now writes Python in a REPL over raw CDP, with no predefined state/action space. Claims: same models up to 50% better, 2-5x cheaper, 2-3x faster, SOTA web agent; asks users to pin versions with `==`.
- **Links:** GitHub https://github.com/browser-use/browser-use · release 1.0.1 https://github.com/browser-use/browser-use/releases/tag/1.0.1 · PyPI https://pypi.org/project/browser-use/
- **License:** MIT.
- **Size and hardware:** Python library; hosted option is Browser Use Cloud (stealth browsers, hosted agent API).
- **Release:** Browser Use; 1.0.0 announced Nov 10, 2026; PyPI 1.0.1 uploaded Nov 10, 2026.

### BeeLlama.cpp v0.5.0 Preview with SINQ quantization
Post: https://x.com/i/status/2120223380896972860 (@Anbeeld)
- **What it is:** First SINQ (Sinkhorn-Normalized Quantization, from the KVarN authors) implementation in the llama.cpp ecosystem, in the BeeLlama.cpp fork. SINQ can be added to an existing GGUF quant recipe to lower error vs BF16. Demo: Bartowski's Qwen 3.5 9B GGUF recipes reproduced with SINQ; post reports lower KLD for every recipe, largest gains at 6 and 8 bits, and Bartowski+SINQ ahead of Unsloth GGUFs on most of the Pareto frontier. Author notes: configs hand-selected via A/B testing, SINQ GGUFs run only on BeeLlama.cpp v0.5.0 for now, larger models (e.g. Qwen 3.8 27B) to follow.
- **Links:** https://github.com/Anbeeld/beellama.cpp · release https://github.com/Anbeeld/beellama.cpp/releases/tag/preview-v0.5.0
- **License:** MIT.
- **Size and hardware:** llama.cpp fork (CPU/GPU builds); KV-cache precision and low-bit quant focus.
- **Release:** Anbeeld; preview-v0.5.0 published Nov 10, 2026 (previous v0.4.9 Oct 28, 2026).

### Ash Hart: ~700 tps on single RTX 5090, Qwen 3.8 27B
Post: https://x.com/i/status/2120292846431347076 (@ashxhart; 38s video, no further text)
- **What it is:** Claim of ~700 tokens/s on one RTX 5090 with Qwen 3.8 27B. Same author's earlier post (id 2119133670049239372) reported Qwen 3.8 27B NVFP4 in TensorFold native CLI on Windows 11 / RTX 5090: ~220 tps single-stream decode, ~12,200 tps prefill, >500 tps decode at C=4, "in the next engine release".
- **Links:** TensorFold https://github.com/ashhart/TensorFold ("LLM Inference Engine for Metal, CUDA and Vulkan"). Video content not analyzed; setup (concurrency, quant) for the 700 tps figure is not stated in the post text.
- **License:** see repo (not verified here).
- **Size and hardware:** RTX 5090 32 GB; Qwen 3.8 27B (Qwen, 27B dense).
- **Release:** Post Nov 10, 2026 (~5:09pm CT).

### T3 Code: control from other devices via MCP connector
Post: https://x.com/i/status/2119948325705462260 (@theo)
- **What it is:** Update to T3 Code's remote-control flow: cmd+k "mcp" sets up a connector so other agents can control T3 Code from other devices.
- **Links:** https://github.com/pingdotgg/t3code
- **License:** MIT (per GitHub).
- **Size and hardware:** desktop app.
- **Release:** Posted by Theo (t3.gg) Nov 9, 2026 (~6:20pm CT).

### NInfer on RTX 5090 (via @QwenAIFans, @XniX)
Post: https://x.com/i/status/2120274462331551834
- **What it is:** NInfer, a from-scratch C++/CUDA single-GPU (RTX 5090) inference engine for Qwen3.5/3.6/3.8 dense and MoE (incl. Qwen3.8-Flash-Next) with text/image/video prompts, native MTP, CLI and OpenAI-/Anthropic-compatible HTTP APIs. Post: after trying four other engines, NInfer held at 302 tok/s on Qwen3.8-27B. Repo's published figures for Qwen3.8-27B NVFP4: 147.7 tok/s C=1 (MTP3), 922.4 tok/s at C=8; independent measurement 159.6 tok/s decode.
- **Links:** GitHub https://github.com/Neroued/ninfer · weights https://huggingface.co/neroued/Qwen3.8-27B-nvfp4-NInfer · independent results https://niklaslenz.com/v2/qwen38-27b-nvfp4-ninfer-mtp3-5090/
- **License:** NInfer Apache-2.0; NVFP4 artifact tagged Apache-2.0 (base Qwen/Qwen3.8-27B).
- **Size and hardware:** one RTX 5090 (32 GB), CUDA 13.1+; five official artifacts (Qwen3.6-27B, Qwen3.6-27B NVFP4, Qwen3.8-27B, Qwen3.8-27B NVFP4, Qwen3.6-35B-A3B).
- **Release:** Neroued; repo last pushed Nov 10, 2026.

### RustingStrata: DeepSeek-V4.1-Flash (249 GB) on RTX 3060 12GB
Post: https://x.com/i/status/2120169614751502699 (@TeksEdge; quotes https://x.com/i/status/2119648679812350066)
- **What it is:** RustingStrata, a pure-Rust inference engine for Qwen GGUF models (Qwen3 to Qwen3.8, dense and MoE) with CUDA/Vulkan, hybrid CPU+GPU experts, MTP speculative decoding and OpenAI/Anthropic-compatible server. New DeepSeek path: DeepSeek-V4.1-Flash IQ2_XXS (249 GB weights) on RTX 3060 12GB + 30 GB RAM, experts streamed from SSD with ~9 GB GPU LRU expert cache. Developer-reported 2-3.6 tps vs llama.cpp 0.3-1.5 tps; prefill very slow, context capped at 4K, no sampling/tool calls in the DeepSeek path yet.
- **Links:** GitHub https://github.com/RustingStudio/RustingStrata (latest release v1.2.1, Nov 8, 2026) · model https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash
- **License:** custom (source-available; GitHub reports NOASSERTION).
- **Size and hardware:** 249 GB weights; RTX 3060 12GB, 30 GB RAM, SSD.
- **Release:** RustingStudio; post Nov 10, 2026.
