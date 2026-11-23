# @Steady_Alex bookmarks — 2026-11-22

### 2124165896948347118 — llama.cpp fork with faster Inkling 2 Mini on CUDA
- Post: https://x.com/JacksonAtkinsX/status/2124165896948347118 (JacksonAtkinsX, Nov 21 2026; reply to https://x.com/JacksonAtkinsX/status/2124165894188511501 claiming 4x prefill and 37% decode speedup for Inkling-2-mini)
- Repo: https://github.com/realugbun/llama.cpp (branch inkling2-speed; fork of ggml-org/llama.cpp, created Nov 21 2026) — license MIT; four commits adding fused CUDA kernels (ggml/src/ggml-cuda/inkling2.cu); build with -DGGML_CUDA=ON.
- README benchmarks: RTX 5060 Ti 16GB (Inkling-2-Mini-UD-IQ1_S) prefill 2.0x-4.1x, decode +37-39%; Tesla V100 32GB (UD-Q4_K_XL) prefill 1.6x-4.9x, decode +59-68%.

## 3:53pm CT run

### PCIe switch-card diagram post (@Cavemtech)
- Post: https://x.com/Cavemtech/status/2124390517823660317 (posted 2026-11-22 00:32 CT; id 2124390517823660317)
- What it is: hardware explainer with a diagram. Claims about $700 of parts (PCIe switch card, SlimSAS/MCIO-style cables, riser boards; GPUs and drives not included) turns one x16 slot into five full-bandwidth x16 GPU connections.
- Specs stated in the post: switch card with x16 host interface, PCIe Gen4/Gen5, about 96 lanes total (16 up to CPU, 80 down); 10 x8 cable ports (two per x16 link); riser boards taking 2x x8 cable inputs to one x16 slot with auxiliary power; blower-style GPUs.
- Links: no repo, model or product page given in the post. License: n/a. Source: X post by @Cavemtech.

## 11:49pm CT run

### 2124506381583880574 — flashbrowse (Rust AXTree headless browser / MCP server for AI agents)
- Post: https://x.com/nhrdev/status/2124506381583880574 (@nhrdev, Nov 22 2026 08:12 CT). Claims 131,319 tokens reduced to 1,719 on the same page with the same Chrome (23x fewer than Puppeteer); MCP native.
- Repo: https://github.com/nhrbuilds/flashbrowse (created Nov 8 2026; releases v1.0.1 Nov 22 03:29 CT, v1.0.2 Nov 22 08:01 CT) — license Apache-2.0; description "Token-compressed, AXTree-native headless browser and MCP server for AI agents. Sub-100ms CDP automation in pure Rust."
- Hardware: no GPU or model; single Rust binary driving Chrome over CDP.
