# Steady_Alex bookmarks, 2026-11-20

## iris-bookmarks-2026-11-20 (12pm CT run)

### Maya v1.1.69: Hy4-Flash speed update (post 2123706854924489090)
- **What it is:** Release announcement by @PeasantSmith (posted 2026-11-20 03:15 CT) for Maya v1.1.69, the Project Maya engine running Tencent Hy4-Flash. Post claims: drafting on 8-12 GB cards with a small DFly2 drafter (up to +29% on an RTX 3050 8 GB); AMD Strix and Gorgon Halo prompts 2-2.5x faster, drafting ~30% faster; NVIDIA long prompts up to +56% at 128K.
- **Links:** post https://x.com/PeasantSmith/status/2123706854924489090 · repo https://github.com/alesha-pro/project-maya (no GitHub Releases page entries) · base model https://huggingface.co/tencent/Hy4-flash
- **License:** Project Maya repo MIT; base model Tencent Hy License.
- **Not novel:** version update to an already-filed engine (see maya-hy4f above).

## ~11:50pm CT run (2 new bookmarks)

### Inkling 2 Mini (Thinking Machines Lab) — bookmark via @UnslothAI
- Post: https://x.com/UnslothAI/status/2123873656069877899 (Nov 20 2026); quoted official post https://twitter.com/thinkymachines/status/2123871643797995872
- What: open-weight multimodal (text+image in, text out) MoE, ~26.4B params, looped-transformer architecture; post cites 48.2% on DeepSWE v1.1.
- Weights: https://huggingface.co/thinkingmachines/Inkling-2-Mini (publisher: thinkingmachines, ModelOpt 8-bit, last modified Nov 20 2026)
- GGUF: https://huggingface.co/unsloth/Inkling-2-Mini-GGUF (UD quants 7.76 GB IQ1_S to 22.87 GB Q8_K_XL; UD-Q4_K_M 16.61 GB)
- Run guide: https://unsloth.ai/docs/models/inkling-2-mini
- License: Apache 2.0. Hardware: post says runs on 16GB RAM.

### SSD as the limiting factor for local AI — @tomgreenwald
- Post: https://x.com/tomgreenwald/status/2123875212093747663 (Nov 20 2026)
- What: thread/post on ultra-sparse MoE models and SSD bandwidth; cited figures: Qwen 3.8 Flash Next 180B total/~6B active (~3%), GLM 5.3 Flash 321B/~18B (~6%), DeepSeek V4.1 Flash 552B/~16B active. Commentary post, no release or repo.

