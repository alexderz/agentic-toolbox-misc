# OrcaRouter: cyber and uncensored DeepSeek models

Checked 2026-10-26 ~9:30pm CT, at Alex's request (in chat). Facts as published by OrcaRouter and on Hugging Face as of that time.

## What OrcaRouter is

- OpenAI-compatible API gateway that routes to OpenAI, Anthropic, Google, DeepSeek, xAI, Qwen, Kimi, MiniMax, Z.ai, Kling, and ByteDance Seedance. It says it adds no markup to provider prices and lists 200+ models.
- Site: https://www.orcarouter.ai (orcarouter.com redirects here)
- Docs: https://docs.orcarouter.ai/introduction · Models: https://docs.orcarouter.ai/getting-started/models · Catalog dump: https://www.orcarouter.ai/llms-full.txt
- Signup: https://www.orcarouter.ai/register · Login: https://www.orcarouter.ai/login
- Hugging Face org: https://huggingface.co/orcarouter

## Hosted cyber + uncensored DeepSeek model (API)

### OrcaCyber: DeepSeek V4.1 Flash Abliterated: `orca/orcacyber-flash-1.0`
- Page: https://www.orcarouter.ai/models/orca/orcacyber-flash-1.0
- Made by OrcaCyber (OrcaRouter's own line). Released 2026-10-23.
- Base: DeepSeek V4.1 Flash. "Abliterated" means refusal behavior has been removed. OrcaRouter describes it as the cost-efficient Flash tier of OrcaCyber for vulnerability research and reproduction, exploit/PoC development, pentest and red-team tooling, auditing, malware/binary analysis, log and network triage, and detection engineering.
- Vendor-reported scores: CyberGym 88.1, SEC-Bench Pro 62.8, Terminal-Bench 2.1 90.6, DeepSWE v1.1 74.2, GPQA Diamond 90.9.
- Context 1M (1,048,576); max output 393K. Input: text + image. Output: text. Supports tools, JSON/structured output, and reasoning (thinking/non-thinking, selectable effort).
- Price: $0.80/M input, $1.60/M output. Zero Data Retention is available.
- Endpoints: /v1/chat/completions, /v1/responses, /v1/messages.
- Access: locked. The public API record says `required_tier: sec-uncensored` and `required_band: offensive`. It requires the Security Research tier: a work-domain email, a passkey, a $0 card check (prepaid cards not accepted), acceptance of the Security AUP, and a review. Some workspaces are also asked for an ID check, a DNS record, a recorded engagement, or the offensive-capability terms. Without the tier, `/v1/models` does not list it and calls return 403.
- License: not listed on OrcaRouter (empty field). No Hugging Face link on the model page.
- Access docs: https://docs.orcarouter.ai/getting-started/cyber-models · Access page: https://www.orcarouter.ai/research · AUP: https://www.orcarouter.ai/security-aup · Offensive terms: https://www.orcarouter.ai/security-offensive-terms · Cyber catalog: https://www.orcarouter.ai/models?tier=cyber

### Other OrcaCyber hosted models (base model not disclosed / not DeepSeek)
| ID | Released | Price in / out per M | Context / max out | Note |
|---|---|---|---|---|
| `orca/orcacyber-zero-1.0` | 2026-09-17 | $3.00 / $7.50 | 1M / 128K | Post-trained for cybersecurity; vendor reports CyberGym L1 98.07% pass@1. Base not stated. |
| `orca/orcacyber-zero-1.5` | 2026-10-10 | $3.00 / $7.50 | 1M / 128K | Successor to Zero 1.0; vendor reports CVE-Bench 95.8%, Cybench 100%, SWE-bench Pro V2 76.5%. Base not stated. |
| `orca/orcacyber-ultra-1.0` | 2026-10-17 | $5.00 / $10.00 | 1M / 131K | "Trillion-parameter" cyber series flagship. Base not stated. |
| `orca/orcacyber-mimo-flash` | — | $0.80 / $1.60 | 1M / 128K | MiMo V2.6 Flash Abliterated (Xiaomi MiMo base, not DeepSeek). |

Pages: https://www.orcarouter.ai/models/orca/orcacyber-zero-1.0 · https://www.orcarouter.ai/models/orca/orcacyber-zero-1.5 · https://www.orcarouter.ai/models/orca/orcacyber-ultra-1.0 · https://www.orcarouter.ai/models/orca/orcacyber-mimo-flash

OrcaRouter also hosts "obsidian/" builds described as giving "direct, complete responses," all non-DeepSeek: `obsidian/qwen3.8-27b`, `obsidian/qwen3.6-35b-a3b`, `obsidian/gemma-4-26b-a4b`.

## Open-weight uncensored DeepSeek repos from the orcarouter Hugging Face org
All are gated on Hugging Face (`gated: auto`, so access is granted automatically after accepting the terms) and MIT-licensed. Sizes are the total repo file sizes.

| Repo | Base | Created | Size |
|---|---|---|---|
| [orcarouter/DeepSeek-V4.1-Flash-1017-abliterated-GGUF](https://huggingface.co/orcarouter/DeepSeek-V4.1-Flash-1017-abliterated-GGUF) | orcarouter/DeepSeek-V4.1-Flash-1017-abliterated (not public) ← DeepSeek V4.1 Flash 1017 | 2026-10-22 | Mix-128G 224.6GB, Mix-256G 346.4GB, mmproj ~1GB, imatrix 1.6GB. Tags: abliterated, uncensored, ai-red-team |
| [orcarouter/DeepSeek-V4.1-Flash-Uncensored-MLX](https://huggingface.co/orcarouter/DeepSeek-V4.1-Flash-Uncensored-MLX) | deepseek-ai/DeepSeek-V4.1-Flash | 2026-09-11 | 2-bit 259.7GB, 3-bit 435.8GB, 4-bit 554.2GB (Apple Silicon / MLX) |
| [orcarouter/DeepSeek-V4-Flash-Vision-Uncensored](https://huggingface.co/orcarouter/DeepSeek-V4-Flash-Vision-Uncensored) | deepseek-ai/DeepSeek-V4-Flash-Vision-Exp | 2026-09-02 | 167.8GB safetensors (FP4/FP8) |
| [orcarouter/DeepSeek-V4-Flash-Vision-Uncensored-GGUF](https://huggingface.co/orcarouter/DeepSeek-V4-Flash-Vision-Uncensored-GGUF) | above | 2026-09-02 | MXFP4 156.4GB |
| [orcarouter/DeepSeek-V4-Flash-Vision-Uncensored-MLX](https://huggingface.co/orcarouter/DeepSeek-V4-Flash-Vision-Uncensored-MLX) | above | 2026-09-02 | 156.2GB |

The model cards sit behind the gate; hardware notes are not public beyond the GGUF mix names (128G / 256G).

Related cyber repos in the same org that are not DeepSeek: [OrcaCyber-Nano-1.0](https://huggingface.co/orcarouter/OrcaCyber-Nano-1.0) (GGUF, license "other") and [OrcaSAQ-2-Cyber-27B-Uncensored-GGUF](https://huggingface.co/orcarouter/OrcaSAQ-2-Cyber-27B-Uncensored-GGUF) (Qwen3.8-27B base, Apache-2.0).

## Official DeepSeek models on OrcaRouter (context)
| ID | In / out per M | Context |
|---|---|---|
| `deepseek/deepseek-v4.1-flash` | $0.15 / $0.60 | 1M |
| `deepseek/deepseek-v4.1-flash-1017` | $0.15 / $0.60 | 1M |
| `deepseek/deepseek-v4.1-flash-free` | free | 1M |
| `deepseek/deepseek-v4-pro` | $0.66 / $1.98 | 1M |
| `deepseek/deepseek-v4-pro-0813` | $0.66 / $1.98 | 1M |
| `deepseek/deepseek-v4-flash` | $0.22 / $0.66 | 1M |
| `deepseek/deepseek-v4-flash-0731` | $0.22 / $0.66 | 1M |
| `deepseek/deepseek-v4-flash-free` | free | 1M |
| `deepseek/deepseek-v4-flash-vision-exp` | $0.22 / $0.66 | 1M |
| `deepseek/deepseek-chat` (V3 alias) | $0.22 / $0.66 | 1M |
| `deepseek/deepseek-reasoner` (legacy alias) | $0.24 / $0.73 | 1M |

Model pages follow the pattern https://www.orcarouter.ai/models/deepseek/<id>.
