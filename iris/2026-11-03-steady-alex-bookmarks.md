# @Steady_Alex bookmark scan, Nov 3 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Tue Nov 3, 2026 ~9:20am CT. Baseline: [Nov 2 scan](2026-11-02-steady-alex-bookmarks.md) (145 total).

## Summary

- **New vs baseline:** 6 ids (all above the Nov 2 set on page 1).
- **Total:** 151 if no baseline ids were removed.
- **Memes skipped:** none (Memes folder unchanged, 2 items).
- **Folders:** no new folders (still Moodils, Keep an eye on this, Cool tech to try, Memes, Cyber). Moodils +5, Keep an eye on this +1.

## Moodils

### DeepSeek-V4.1-Flash-1017-obliterated (OBLITERATUS / Pliny)
@elder_plinius, Oct 31 10:21pm CT ("Happy Halloween!"). https://x.com/elder_plinius/status/2116732431491621144
- **What it is:** refusal-direction ablated DeepSeek-V4.1-Flash-1017, made with the OBLITERATUS tool using the failspy method. Card results: refusal rate 4% (2 of 50 eval prompts), KL divergence 0.1305 nats vs original, coherence 100%, capability 6/6 checks. On the 842-prompt OBLITERATUS corpus (838 compared), full refusals 81.62% (original) vs 4.30% (ablated).
- **License:** MIT (weights). OBLITERATUS tool repo is AGPL-3.0.
- **Size:** BF16 safetensors, ~754.6B params, 83 shards, ~1.51 TB total. Transformers library tag.
- **Release:** HF repo created Oct 23 2026, last modified Oct 30 2026.
- **Links:** https://huggingface.co/OBLITERATUS/DeepSeek-V4.1-Flash-1017-obliterated · tool https://github.com/elder-plinius/OBLITERATUS · base https://huggingface.co/deepseek-ai/DeepSeek-V4.1-Flash-1017

### LFM3-1.7B-abliterated (OrcaRouter)
@OrcaRouter, Nov 2 4:23am CT. https://x.com/OrcaRouter/status/2117200982740508787
- **What it is:** abliterated version of Liquid AI LFM3-1.7B (family facts in [Oct 29 scan](2026-10-29-steady-alex-bookmarks.md)). Post: "Built for local agents and edge AI."
- **License:** other, `lfm1.0` (Liquid AI LFM Open License).
- **Size:** 1.73B params, single BF16 safetensors 3.46 GB; ships custom LFM3 modeling code (Transformers).
- **Release:** HF repo created Nov 2 2026 4:11am CT. The repo is gated (access request / HF login required to read the card and files).
- **Links:** https://huggingface.co/orcarouter/LFM3-1.7B-abliterated · base https://huggingface.co/LiquidAI/LFM3-1.7B · publisher https://www.orcarouter.ai

### SenseNova-Loop-9B-Preview (SenseNova)
@ModelScope2022, Nov 2 12:18am CT. https://x.com/ModelScope2022/status/2117139176168759353
- **What it is:** open-weight multimodal (text + image in, text out) model for long-context and agent work. Looped decoder: layers 4–27 run twice with shared weights, so 56 layer executions from 32 distinct layers (~9B stored params, ~14.6B "inference parameters"). Two-stream manifold-constrained hyper-connections (mHC) in the loop; hybrid attention (3 linear + 1 full per 4-layer group). Trained up to 262,144-token sequences. MTP speculative decoding available; Dspark and Dflash2 in training. Post cites BIRD-Dev 71.38, WorkBuddy Bench 66.89, AIDABench 58.87 (team-reported; leads 6 of 8 tasks in its comparison). Technical report TBD.
- **License:** Apache-2.0.
- **Size and hardware:** BF16 backbone (FP32 mHC routing params), ~38.2 GB repo. Checked environment: Transformers 5.18.0, PyTorch 2.11.0 + CUDA 13.0; card example runs on a single GPU; custom code. Post lists Transformers, LightLLM, SGLang and vLLM deployment paths. Third-party GGUF/NVFP4 builds exist on HF (e.g. AtomicChat/SenseNova-Loop-9B-Preview-GGUF).
- **Release:** card news dated Oct 30 2026; HF repo created Oct 28 2026, updated Nov 2 2026.
- **Links:** https://huggingface.co/sensenova/SenseNova-Loop-9B-Preview · https://modelscope.ai/models/SenseNova/SenseNova-Loop-9B-Preview · https://github.com/OpenSenseNova/SenseNova-Loop · GGUF https://huggingface.co/AtomicChat/SenseNova-Loop-9B-Preview-GGUF

### Qwen3.8-27B-Longbook27-v2 (second post)
@LiLensss, Nov 2 12:31am CT (Chinese). https://x.com/LiLensss/status/2117142551132315673
- **What it is:** Chinese-language write-up of the same model filed in the [Nov 2 scan](2026-11-02-steady-alex-bookmarks.md) (all-GDN linear-attention Qwen3.8-27B variant). Post figures: 262K input in ~55 GB VRAM; layer-wise distillation plus LoRA r32 recovery; NF4 4-bit ~17 GB, fits one 24 GB 3090/4090.
- **Links:** https://huggingface.co/summerAIO/Qwen3.8-27B-Longbook27-v2

### Project Maya v1.1.50 (Peasant Smith / mw00)
@PeasantSmith, Nov 2 11:22am CT. https://x.com/PeasantSmith/status/2117306270352883976
- **What it is:** release of the Maya local inference app (prior: v1.1.47 in Nov 2 scan).
- **v1.1.50 changes (Nov 2 10:43am CT):** Models page (download/load/unload/delete with sizes); Ollama-style model API (`/api/tags`, `/api/ps`, `/api/show`, `/api/chat`, `/api/generate`, `/api/pull`, `/api/delete`, swap-on-request, `keep_alive`); Turbo button (greedy, no thinking, 32K ctx on GLM/MiniMax, expert skipping; up to ~24% faster decode per post); thinking budget setting (default 32768, GLM Maya-XS 8192); new GLM-5.3-Flash Maya-XS quant ~73 GB for 64 GB RAM + 24 GB GPU at 128K context (`glm-maya-xs`); DeepSeek long prompts up to ~19% faster when experts live in RAM; `/tokenize`, `/detokenize`, `response_format` community PRs.
- **Since then:** v1.1.51 (Nov 3 2:31am CT): DeepSeek tensor-parallel expert split follows free VRAM per GPU (~10% more experts in VRAM, up to 10% faster decode; `DS4_TP_SHARES=off` reverts); long prompts ≥~10K up to ~12% faster with most experts in RAM; multi-conversation stop fix; README in Japanese, Simplified Chinese, Brazilian Portuguese.
- **License:** MIT.
- **Links:** https://github.com/mw00/project-maya/releases/tag/v1.1.50 · https://github.com/mw00/project-maya/releases/tag/v1.1.51 · https://github.com/mw00/project-maya

## Keep an eye on this

### Pithos (benmaster82)
@TeksEdge, Nov 1 8:30pm CT. https://x.com/TeksEdge/status/2117081763944026592
- **What it is:** dependency-free C11 inference engine for Liquid AI LFM2 / LFM2-MoE / LFM2.5 / LFM3 GGUF models, single executable: terminal chat, OpenAI-compatible server (prompt reuse across turns), "Pandora" web agent (web search, files, MCP servers), terminal agent (safe or autonomous mode). CPU kernels AVX2/AVX/NEON; optional OpenCL (hot experts in VRAM, rest on CPU, cold experts streamed from disk) and Direct3D 12 (Windows/Xbox). Windows, Linux, macOS on x86-64 and ARM64; Xbox One app in Developer Mode.
- **Reported performance:** LFM2.5-24B-A2B Q4_K_M (13.5 GB) on i5-10500H, 16 GB RAM, GTX 1650 Max-Q 4 GB: Pithos 17.5–21.9 tok/s vs llama.cpp CUDA 11.2–11.3 tok/s (developer-reported, head-to-head dated Oct 24). LFM3-1.7B ~55 tok/s with GPU, ~20 CPU-only; 29.5 tok/s on Xbox One GPU.
- **License:** MIT.
- **Release:** GitHub repo created Oct 27 2026, last push Nov 3 2026; no tagged releases.
- **Links:** https://github.com/benmaster82/Pithos · https://benmaster82.github.io/Pithos/

---

## Evening run (pulled Tue Nov 3, 2026 ~8:00pm CT)

Baseline: the ~9:20am run above (151 total). 7 new bookmark ids on page 1, 0 memes. Total 158 if nothing was removed. **New folder:** "tech updates" (id 2117773554817126630), holding 1 item (Maya v1.1.51). Moodils +2, Cool tech to try +1, Keep an eye on this +3, tech updates +1.

### Moodils

#### NorthCUA Nano / Mini / Pro (beipo-ai)
@QwenAIFans, Nov 3 5:08pm CT (Chinese). https://x.com/QwenAIFans/status/2117755815809732726
- **What it is:** open-weight computer-use agent model family built on Qwen3.5 (image-text-to-text). Takes user requests, screenshots and interaction history; outputs reasoning, responses and tool calls for a desktop or browser runtime. GUI coordinates use a 0–1000 normalized space. The card says the official NorthCUA Harness is required for computer-use tasks.
- **Family:** Nano 9B dense; Mini 35B total / 3B active MoE; Pro 397B total / 17B active MoE (`qwen3_5_moe`). HF safetensors param totals: Nano 9.41B, Mini 35.11B, Pro 396.80B.
- **Reported results (technical report, not re-measured on the released files):** OSWorld-Verified RL success Nano 78.90 / Mini 85.30 / Pro 88.64; WebArena-Verified 67.16 / 70.43 / 73.89; ScreenSpot-Pro (SFT) 72.87 / 92.41 / 93.30; OSWorld-G (SFT, best of 3 runs) 82.98 / 87.94 / 90.96. Pro OSWorld 2.0 mean partial credit 66.80% (108 tasks). Report is 121 pages.
- **License:** Apache-2.0.
- **Hardware:** Transformers with `Qwen3_5ForConditionalGeneration` (export config records Transformers 5.20.2), PyTorch, Accelerate. Card gives no specific GPU requirement.
- **Release:** HF repos created Oct 30 (Pro) and Nov 1 2026 (Nano, Mini), updated Nov 3 2026.
- **Links:** https://huggingface.co/beipo-ai/NorthCUA-Pro · https://huggingface.co/beipo-ai/NorthCUA-Mini · https://huggingface.co/beipo-ai/NorthCUA-Nano · harness https://github.com/china-qijizhifeng/NorthCUA-Harness · project page https://beipo.top/blog/northcua/ · report https://arxiv.org/pdf/2611.02102v1

#### Crouton Alpha (stealth model on OpenRouter)
@aitrackerbot, Nov 3 2:29pm CT. https://x.com/aitrackerbot/status/2117715857237258558
- **What it is:** stealth (unnamed-vendor) model listed on OpenRouter as `stealth/crouton-alpha`. OpenRouter description: "a lightweight model built for scalable coding, agentic, and multimodal workflows… agentic sub-tasks, tool use, and document analysis in high-volume, repeated work."
- **Attribution (unconfirmed, per post):** looks like Meta; OpenCode's page lists the same 21 blocked countries as Meta's model API; fails on a rare Japanese word that every Meta Muse model fails on (93 other models: 0 misses); only Meta's Muse listings on OpenRouter share its reasoning-effort settings. Post says "Not confirmed."
- **Specs (OpenRouter API):** input text, image, file, audio, video; output text. Context 1,048,576 tokens; max completion 943,718. Reasoning mandatory, efforts max / xhigh / high / medium / low / minimal (default max). Supports tools, structured outputs. Price $0 prompt / $0 completion. Single provider "Stealth". Listed Nov 2 2026 7:38pm CT.
- **License / weights:** hosted only, no Hugging Face id.
- **Links:** https://openrouter.ai/stealth/crouton-alpha

### Cool tech to try

#### Weight-space programming: Qwen 3.8 27B reading model weights (Simon Willison)
@simonw, Nov 3 10:31am CT. https://x.com/simonw/status/2117655816581071203
- **What it is:** blog post reproducing one experiment from the "Sparks of Weight-Space Programming" post (Rikiya Takehi, Jayden Teoh, Alex Zhang, Omar Khattab), which reports GPT-6 Astra identifying what a network was trained to do from raw weights given as text, writing small game-playing networks from scratch, and editing 0.016% of Qwen3.5-0.8B weights to raise MATH-500 from 7.9% to 48.1%.
- **Willison's result:** with no tools, Qwen 3.8 27B (17 GB build in LM Studio, long context required) identified Pac-Man (46m 12s, 43,506 reasoning tokens, 72% confidence), Pong (1h 4m 54s, 75%) and Breakout (52m 25s, 88%) from the policy-network weight prompts; it failed on Freeway. Kimi K3.1 Pro via OpenRouter identified Breakout in 9m 41s, 19,493 reasoning tokens.
- **Tools used:** `llm` CLI with `llm-lmstudio` / `llm-openrouter` plugins (Apache-2.0); prompts from the paper's log repo.
- **Links:** https://simonwillison.net/2026/Nov/3/qwen-can-interpret-model-weights/ · prompts https://github.com/RikiyaT/lm_understand-logs (exp1_which_game)

### Keep an eye on this

#### Weight-space programming from scratch (Chandan Singh, csinva)
@0x0SojalSec, Nov 2 7:11pm CT. https://x.com/0x0SojalSec/status/2117424378807976074
- **What it is:** experiment where Claude, as an autonomous coding agent, set every weight of a small GPT-style transformer by hand (no training, optimizer or backprop) and wrote 959 "weight-space programs" across 13 tasks. All 10 algorithmic tasks (addition, multiplication, sorting, parity, GCD, decimal-to-binary, etc.) reached 100% on 200 eval examples within three attempts; runs then compressed the programs (e.g. decimal-to-binary 124,000 → 192 params; parity program 174 params, 35 nonzero). Each head and neuron has a written explanation. The report states the 3 language tasks (SST-2, MRPC, SNLI) are affected by an evaluation flaw (eval examples in the readable pool; SNLI 100% invalid) and that all programs share one eval seed.
- **License:** none declared on the GitHub repo.
- **Release:** report dated Nov 2 2026; repo created May 15 2026, last push Nov 3 2026.
- **Links:** https://csinva.io/weight-space-programming-autoresearch/analyze/toy_examples/report.html · https://github.com/csinva/weight-space-programming-autoresearch

#### NVIDIA Auto Ontology
@Ldataengineer, Nov 2 6:46pm CT. https://x.com/Ldataengineer/status/2117418155647684676
- **What it is:** open-source Python framework for a semantic, graph-based "context layer" between AI agents and databases. Discovers database metadata and drafts an ontology of business terms, grounds agents on those terms, validates generated SQL against certified definitions, exposes everything through MCP (9 read-only tools, no raw-table browsing tool), CLI or API, and feeds certified corrections back. Returns the answer, the SQL run and the rows.
- **Backends:** Databricks, Postgres, Snowflake, DuckDB. Defaults to NVIDIA Nemotron models; any OpenAI-compatible endpoint works. Deploys with Docker Compose or Helm. Ships a BIRD eval harness (1,534 questions) without published scores; the post notes the "90% faster" claim is NVIDIA's own testing and that without HashiCorp Vault database passwords are stored unencrypted in Postgres (per README). Not accepting outside contributions.
- **License:** Apache-2.0.
- **Release:** GitHub repo created Apr 27 2026, last push Nov 3 2026; 3,003 stars at time of check; no tagged releases.
- **Links:** https://github.com/NVIDIA/auto-ontology

#### dsh-jailbreak-workflow / dsh-workflows (Minglink)
@NFT_Chen, Nov 2 11:19pm CT (Chinese). https://x.com/NFT_Chen/status/2117486881399284175
- **What it is:** "soft workflow" plugin for DeepSeek Harness (DSH 0.2.x): design a flow on a canvas, compile it into one plan prompt, and the model in the current session executes it (branches, loops, parallel steps, rollback; no separate execution engine). Can export a flow as a Skill. The companion pack repo publishes a 15-step "破甲制作" (jailbreak-prompt-making) research pipeline: 200+ probes, refusal-pattern analysis, custom prompt generation, API verification, and an output bundle of prompt file, usage manual and research report; bundles a jailbreak-research skill with 10 test scripts and 4 prompt templates. Install per post: `dsh plugin --profile web add @xiaoso/dsh-workflow-lite`, then import the `.wflite.zip` in DSH's Workflow hub. Marked experimental.
- **License:** plugin repo MIT (covers its own code only; third-party notices file); workflows repo MIT. Node 22+.
- **Release:** both repos created Nov 1 2026, last push Nov 3 2026 (347 and 118 stars at check).
- **Links:** https://github.com/Minglink/dsh-jailbreak-workflow · https://github.com/Minglink/dsh-workflows · DeepSeek Harness https://github.com/deepseek-ai/deepseek-harness

### tech updates (new folder)

#### Project Maya v1.1.51
@PeasantSmith, Nov 3 2:47am CT. https://x.com/PeasantSmith/status/2117539150362448281
- Release already summarized in the morning section above (under Project Maya v1.1.50, "Since then"). Post adds: CYBER-FROST gets a thinking Off button. MIT. https://github.com/mw00/project-maya/releases/tag/v1.1.51
