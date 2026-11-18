# @Steady_Alex bookmarks, 2026-11-18

## ~8am CT run
New bookmark: 2122913211821551716 (post by an account replying to @TencentHunyuan, Nov 2026). All other newest-15 bookmarks already filed.

### Hy4-Flash open weights (Tencent Hy) (post 2122913211821551716)
- **What it is:** post says Hy4-Flash weights are open: 220B total parameters (including 64B Engram parameters), 12B active per token, native text and image input, context up to 1M tokens, Tencent Hy License. Follows the Nov 16 API release filed in 2026-11-16 note (post 2122215948728045857).
- **Links:** post https://x.com/i/status/2122913211821551716 · Hugging Face https://huggingface.co/tencent/Hy4-flash · FP8 https://huggingface.co/tencent/Hy4-flash-FP8 · base https://huggingface.co/tencent/Hy4-flash-base · GGUF https://huggingface.co/AngelSlim/Hy4-flash-GGUF · GitHub https://github.com/Tencent-Hunyuan/Hy4-flash · official page https://hy.tencent.ai/research/hy4-flash · ModelScope https://modelscope.cn/models/Tencent-Hunyuan/Hy4-flash
- **License:** Tencent Hy License (HF license "other"; text at https://huggingface.co/tencent/Hy4-flash/blob/main/LICENSE).
- **Size and hardware:** Hugging Face metadata: 220.25B parameters (instruct), 220.26B (FP8 repo), 219.4B (base); transformers, image-text-to-text, MoE.
- **Release:** Tencent Hy; HF repos created Nov 16-17, 2026 (UTC; instruct repo 2026-11-17T03:44Z), last modified Nov 18 2026 04:24Z.

## ~4pm CT run
New bookmark: 2123075544975568956 (post by @atomic_chat_hq, 2026-11-18 15:27Z). All other newest-15 bookmarks already filed.

### AtomicChat Hy4-flash-GGUF quant of Tencent Hy4-Flash (post 2123075544975568956)
- **What it is:** quantized GGUF release of Tencent Hy4-Flash by atomic.chat. Post says the 220B model runs locally on a 64 GB machine because 63.5B parameters are an Engram lookup table read a few KB per token and kept on SSD. Base model filed in the ~8am note (post 2122913211821551716).
- **Links:** post https://x.com/atomic_chat_hq/status/2123075544975568956 · Hugging Face https://huggingface.co/AtomicChat/Hy4-flash-GGUF · base model https://huggingface.co/tencent/Hy4-flash
- **License:** HF license "other" (Tencent Hy License inherited from base tencent/Hy4-flash; LICENSE file in repo).
- **Size and hardware:** HF metadata: 218.9B parameters, architecture hy_v4_flash, context length 1,048,576; files: Hy4-flash-AD-IQ2_S-IQ2_XXS (2 GGUF shards), mmproj-Hy4-flash-F16.gguf (vision projector); total file size 84.7 GB.
- **Release:** atomic.chat; HF repo created 2026-11-18 13:37Z, last modified 15:04Z.
