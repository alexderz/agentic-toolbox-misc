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
