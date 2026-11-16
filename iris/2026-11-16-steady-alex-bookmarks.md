# @Steady_Alex bookmarks, Nov 16, 2026

## 12am CT run (Nov 16, 2026)

One bookmark new since the Nov 15 8pm notes (unfiled folder, 0 memes).

### Omarchy A: Omarchy-inspired desktop installer for iPad (post 2122061805719851207)
- **What it is:** the post says "New @omarchy iPad installer coming soon!" (text plus media). It refers to Omarchy A, a community project (not an official Omarchy release): an experimental Omarchy-inspired desktop for Apple A-series devices, built on Arch Linux ARM and reworked for touch. Installed with one command from a Linux/macOS host over USB in DFU mode; boot is tethered (restart needs `orchard launch` on a host). Supported: iPad 6 Wi-Fi (iPad7,5 / J71b); other devices experimental. Needs at least 9 GiB free on the iPad (made via the Resize APFS app) and iPadOS 16 or later. Image uses automatic `tablet` login and passwordless sudo, no disk encryption (stated in README).
- **Links:** post https://x.com/i/status/2122061805719851207 · code https://github.com/OrchardLinux/omarchy-a · releases https://github.com/OrchardLinux/omarchy-a/releases · coverage https://omarchycentral.com/news/omarchy-a-v0-1-0-is-a-one-command-installer-for-an-omarchy-inspired-desktop-on-the-ipad-6/
- **License:** not retrieved.
- **Size and hardware:** iPad 6/7 (GPU acceleration in v0.3.0), host with curl, libusb, OpenSSH, USB data cable; install under 2 minutes per v0.3.0 notes.
- **Release:** OrchardLinux GitHub org; v0.2.0 Oct 31, 2026; v0.3.0 (GPU acceleration on iPad 6 and 7, app switcher, Files touch mode); v0.3.1 Nov 15, 2026 (built on orchard 0.3.1).

## 12pm CT run (Nov 16, 2026)

One bookmark new since the 8am CT run (unfiled folder, 0 memes).

### Hy4 flash (Tencent Hy) (post 2122215948728045857)
- **What it is:** post (Nov 16, 2026 ~12:31am CT) says "Hy4 Flash is released, 160B-N64B-A12B! This model will run well with 96-128GB machine and its low bit quant can even run in 64GB machine!" Tencent's official post (Nov 16, 2026) lists 224B total parameters (including 64B Engram parameters), 12B active per token, natively multimodal, 1M-token context, hybrid attention + LatentMoE + Engram (KV cache 1/24 of Hy3, 1/6 of Hy4), self-distilled from Hy4 plus RL (average output tokens cut 50%), decoding over 150 tokens/s. Tencent states it plans to release Hy4 flash as an open-weight model; as of this run no Hugging Face repo, license or model card was found.
- **Links:** post https://x.com/i/status/2122215948728045857 · official page https://hy.tencent.ai/research/hy4-flash · coverage https://www.orcarouter.ai/blog/tencent-hy4-flash-vs-tencent-hy4
- **API/pricing (per million tokens):** cached input $0.003, input $0.070, output $0.281 (Hy4: $0.042 / $0.834 / $2.501). Available on Tencent Cloud TokenHub (50% off API through Nov 30), free in WorkBuddy through Nov 30, also Yuanbao, WeCom, QQ, ima, Marvis; OpenRouter listed as "soon".
- **License:** none published (weights not released).
- **Size and hardware:** 224B total / 12B active per official page; the post's 160B figure and 64-128GB machine claim are the poster's.
- **Release:** Tencent Hy, Nov 16, 2026. Related: Hy4 preview (Aug 28, 2026, Apache 2.0, 770B/49B active, weights on Hugging Face); Hy4 GA Nov 4, 2026 (no weights).
