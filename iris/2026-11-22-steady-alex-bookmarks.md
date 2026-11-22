# @Steady_Alex bookmarks — 2026-11-22

### 2124165896948347118 — llama.cpp fork with faster Inkling 2 Mini on CUDA
- Post: https://x.com/JacksonAtkinsX/status/2124165896948347118 (JacksonAtkinsX, Nov 21 2026; reply to https://x.com/JacksonAtkinsX/status/2124165894188511501 claiming 4x prefill and 37% decode speedup for Inkling-2-mini)
- Repo: https://github.com/realugbun/llama.cpp (branch inkling2-speed; fork of ggml-org/llama.cpp, created Nov 21 2026) — license MIT; four commits adding fused CUDA kernels (ggml/src/ggml-cuda/inkling2.cu); build with -DGGML_CUDA=ON.
- README benchmarks: RTX 5060 Ti 16GB (Inkling-2-Mini-UD-IQ1_S) prefill 2.0x-4.1x, decode +37-39%; Tesla V100 32GB (UD-Q4_K_XL) prefill 1.6x-4.9x, decode +59-68%.
