# @Steady_Alex bookmark catalog

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Oct 3, 2026 from the X bookmarks API (one page, max_results 100).

Oct 4, 2026 pull: four new bookmarks, still no folders. This note stays the baseline and is not renumbered. Delta: [2026-10-04-steady-alex-bookmarks.md](2026-10-04-steady-alex-bookmarks.md).

## Summary

Access URLs (Hugging Face, API, and signup) were backfilled for the model items below, per Alex on Oct 5.

- **Total bookmarks:** 35
- **Pagination:** finished. The only page returned `result_count` 35 and no `next_token`. Requested page size was 100, so this is the full list the API returned.
- **Post dates:** Sep 13, 2026 1:54pm CT through Oct 1, 2026 9:32pm CT (created_at, converted from UTC). API order is bookmark order, not strictly post date.
- **Folders:** none. `get_users_bookmark_folders` was called twice and both times returned an empty object (`{}`), with no folder ids and no error text. No per-folder bookmark calls were possible. No post is in a folder.
- **What the list is:** almost entirely the late-September local-model wave. Qwen3.8 compression and speed, a few new MoE and stealth launches, one audio day (Sep 23), and agent-harness notes that name Jev, Hermes, and token cost. Two bookmarks are not models: a Framework desktop and a Howdy face-login reply.

### Topics

- **Consumer-GPU inference speed** — 4
- **Extreme compression for local Qwen** — 7
- **Refusal-reduced weights and rehosting** — 3
- **New model launches** — 6
- **Speech and audio models** — 4
- **Agent harnesses, sandboxes, and Jev** — 5
- **Agents that build things** — 3
- **LLM as the recommender** — 1
- **High-RAM local workstation** — 1
- **Linux face login on the XPS** — 1

Raw API pages: `raw/bookmarks-page-001.json`, `raw/folders-page-001.json`.

## Consumer-GPU inference speed

**4 bookmarks.** Tok/s numbers for Qwen-class models on one 3090, a consumer GPU, and Apple Silicon. Methods named: speculative decoding and kernel work (DFlash2, lookup drafts, TensorFold, Strata), not new weights.

Representative posts:

- @Oluwaphilemon1 (FHILY👑), Oct 1, 2026 9:32pm CT. A single RTX 3090 (24GB) is claimed at ~381 tok/s on Qwen3.8-27B by stretching DFlash2 speculative decoding, longer verification blocks, and lookup drafting. https://x.com/Oluwaphilemon1/status/2105848435672764747

  **Access:**

  - Checkpoint: https://huggingface.co/Qwen/Qwen3.8-27B
  - DFlash2: no single HF card. The post describes a decoding method and does not name a draft repo. A Hugging Face search for `DFlash2` returns several community drafts, none linked from the post.

- @coldniko (Niko Veit), Sep 28, 2026 1:08am CT. Same Strata stack: prompt processing for Qwen3.8-Flash-Next on a consumer GPU jumps from 539 to 1290 tok/s, with more kernel work planned. https://x.com/coldniko/status/2104453283255287915

  **Access:**

  - Runtime: https://github.com/Niko1221/Strata
  - Checkpoint: https://huggingface.co/Qwen/Qwen3.8-Flash-Next
  - Strata itself has no HF card. It is an inference stack for that checkpoint.

- @ashxhart (Ash Hart), Sep 25, 2026 7:31pm CT. TensorFold runs draft tokens in parallel lanes on Apple Silicon so one weight read covers more than one token; MLX numbers for Qwen 3.8 27B and Flash Next. https://x.com/ashxhart/status/2103643602937114924

  **Access:**

  - Engine: https://github.com/ashhart/TensorFold (no HF weights of its own).
  - Named checkpoints: https://huggingface.co/Qwen/Qwen3.8-27B · https://huggingface.co/Qwen/Qwen3.8-Flash-Next · Nemotron Lightning: https://huggingface.co/nvidia/NVIDIA-Nemotron-3.5-Lightning-30B-A3B-BF16
  - The post’s MLX 4-bit numbers are engine benchmarks. It does not name a separate quant card.

Also in this topic:

- @coldniko, Sep 29, 2026 3:00pm CT. Niko Veit’s Strata update makes the first 32K tokens of Qwen3.8-Flash-Next 4–10% faster and adds a low-RAM mode. https://x.com/coldniko/status/2105024852742787195

  **Access:**

  - Release linked from the post: https://github.com/Niko1221/Strata/releases/tag/v0.1.26
  - Same checkpoint as the Strata note above: https://huggingface.co/Qwen/Qwen3.8-Flash-Next

## Extreme compression for local Qwen

**7 bookmarks.** How to fit a Qwen3.8-class model into 6–16GB. Ternary Bonsai, Sushi, and OrcaSAQ target agentic coding and tool use. A side thread is memory split for the Qwen image model. Two bench posts: a 3060 overnight Hermes game build, and a 4090 at 65 tok/s.

Representative posts:

- @PrismML (PrismML), Sep 17, 2026 4:03pm CT. PrismML’s Ternary Bonsai 2 27B: about 5.9GB and 9× smaller than fp Qwen3.8 27B, claiming 98.2% of aggregate benchmark score. https://x.com/PrismML/status/2100692248480596348

  **Access:**

  - Weights (Apache 2.0): https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf · base: https://huggingface.co/Qwen/Qwen3.8-27B
  - Runtime the later Hikari post calls official for this format: https://github.com/PrismML-Eng/Bonsai-demo · llama.cpp branch: https://github.com/PrismML-Eng/llama.cpp

- @OrcaRouter (OrcaRouter 🐳), Sep 24, 2026 10:29am CT. OrcaSAQ-2 packs a mixed-precision Qwen3.8 27B into 12GB (from 56GB) for long-horizon coding, terminal, and tool agents. https://x.com/OrcaRouter/status/2103144808412037578

  **Access:**

  - Weights: https://huggingface.co/orcarouter/OrcaSAQ-2-27B (linked from the post) · base: https://huggingface.co/Qwen/Qwen3.8-27B
  - No separate hosted API on the card. It is a local quant.

- @0xSero (0xSero), Sep 17, 2026 5:06pm CT. 0xSero points at PrismML’s ternary Qwen3.8-27B as the strongest local model for 8–16GB VRAM or a 16–24GB Mac. https://x.com/0xSero/status/2100708075325841839

  **Access:**

  - Same Bonsai 2 card: https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf

- @TeksEdge (David Hendrickson), Sep 24, 2026 3:00pm CT. Qwen-Image-2.1 GGUFs down to ~4.6GB so the image model stays in VRAM and the text encoder sits in system RAM, including an uncensored variant. https://x.com/TeksEdge/status/2103212883857543441

  **Access:**

  - GGUF named in the post’s image alt text: https://huggingface.co/abenzerps/Qwen-Image-2.1-Uncensored-GGUF
  - Official base: https://huggingface.co/Qwen/Qwen-Image-2.1

Also in this topic:

- @Beamsters1, Sep 27, 2026 4:15am CT. Beamsters’ Sushi quant of Qwen3.8-Flash-Next at 2.6 bpw, 43.8GB, aimed at 64GB-class machines, with a local pelican demo. https://x.com/Beamsters1/status/2104137834013892803

  **Access:**

  - Quant: https://huggingface.co/beamster/Qwen3.8-Flash-Next-Sushi-2.6bpw · base: https://huggingface.co/Qwen/Qwen3.8-Flash-Next
  - Repo linked from the post: https://github.com/beamivalice/sushi

- @sudoingX, Sep 24, 2026 8:00am CT. A 12GB RTX 3060 running Bonsai 2 through Hermes Agent is said to have built a whole game overnight. https://x.com/sudoingX/status/2103107193016844653

  **Access:**

  - Same Bonsai 2 card: https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf
  - Hermes Agent here is the harness, not a second model.

- @studio_yebisu, Sep 18, 2026 5:18pm CT. A Japanese local bench: Bonsai 2 27B at 64.6 tok/s on a 4090, a simple webpage in ~25 seconds, with 12GB called more than enough. https://x.com/studio_yebisu/status/2101073385744724378

  **Access:**

  - Same Bonsai 2 card: https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf

## Refusal-reduced weights and rehosting

**3 bookmarks.** Three saves are about models that answer where the stock weights refuse. Two are abliteration-style edits of Qwen3.8-27B (a Heretic GGUF, and a ternary Bonsai edited in place so a 12GB card still runs it). The third is Pirate Face rehosting a GLM that Hugging Face removed.

Representative posts:

- @TeksEdge (David Hendrickson), Sep 25, 2026 11:13am CT. A ThinkingCap then Heretic pass on Qwen3.8-27B: fewer thinking tokens, similar accuracy, most refusals removed, packaged as local GGUFs. https://x.com/TeksEdge/status/2103518301238485073

  **Access:**

  - GGUF named in the post’s image alt text: https://huggingface.co/mradermacher/ThinkingCap-Qwen3.8-27B-Uncensored-Heretic-GGUF
  - Source that GGUF card names: https://huggingface.co/OS-Software/ThinkingCap-Qwen3.8-27B-Uncensored-Heretic · base: https://huggingface.co/Qwen/Qwen3.8-27B

- @xiangxiang103 (雨哥向前冲), Sep 25, 2026 6:05am CT. A Chinese writeup of Hikari’s unrestricted Bonsai 2 27B: ternary weights edited in place, 0/40 sensitive refusals, ~7.2GB, meant for a 12GB card. https://x.com/xiangxiang103/status/2103440630257270932

  **Access:**

  - Hikari weights, linked from the post: https://huggingface.co/Hikari07jp/Ternary-Bonsai-2-27B-Abliterated-GGUF
  - BoldingBuilds build also linked there: https://huggingface.co/BoldingBuilds/Ternary-Bonsai-2-27B-Abliterated-PTQ1_0-GGUF
  - Stock Bonsai 2: https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf · runtime: https://github.com/PrismML-Eng/Bonsai-demo

- @thepirateface (Pirate Face), Sep 30, 2026 9:26am CT. Pirate Face says it is hosting an abliterated GLM that Hugging Face banned, pitched as a continuity plan for the model. https://x.com/thepirateface/status/2105303200744292718

  **Access:**

  - The post names `audnai/penc1aw-GLM-5.3-abliterated-for-offensive-cyber`. That exact id returned 401.
  - The `penclaw` spelling loads, and both repos are manually gated: https://huggingface.co/audnai/penclaw-GLM-5.3-abliterated-for-offensive-cyber · relisted weights: https://huggingface.co/audnai/penclaw-GLM-5.3-abliterated
  - Pirate Face profile for the named model: https://pirateface.co/audnai/penclaw-GLM-5.3-abliterated-for-offensive-cyber · rescued listing: https://pirateface.co/audnai/penclaw-GLM-5.3-abliterated

## New model launches

**6 bookmarks.** Open-weight MoEs (Ling-3.1-flash, Naive-N0.5-Flash), Cloudflare’s Clef decision models, and the stealth Space Bunny flash model on both OpenRouter and OpenCode. Rysana V2 is a speed claim with little architecture detail in the post.

Representative posts:

- @AntLingAGI (Ant Ling), Sep 30, 2026 11:33am CT. Ant Ling previews Ling-3.1-flash, a ~560B MoE (~25B active) with up to 1M context, aimed at work, coding, and healthcare, with open-source planned. https://x.com/AntLingAGI/status/2105335205741596911

  **Access:**

  - Hugging Face: no public weights. An inclusionAI-org search shows Ling-3.0 repos and no Ling-3.1 repo. The post says open-source is planned.
  - OpenRouter: https://openrouter.ai/inclusionai/ling-3.1-flash
  - Vercel AI Gateway: https://vercel.com/ai-gateway/models/ling-3.1-flash · free id: https://vercel.com/ai-gateway/models/ling-3.1-flash-free · changelog: https://vercel.com/changelog/ling-3-1-flash-is-now-available-on-ai-gateway
  - OpenCode Zen also lists it as `ling-3.1-flash-free`: https://opencode.ai/docs/zen/

- @naiveailab (NaiveAI), Sep 27, 2026 11:29am CT. NaiveAI releases Naive-N0.5-Flash, a 309B MoE (15.5B active), native 1M context, MIT weights, and a claimed ultrafast inference mode. https://x.com/naiveailab/status/2104247060186951725

  **Access:**

  - Weights: https://huggingface.co/NaiveAI/Naive-N0.5-Flash (linked from the post)
  - Blog: https://naive.ai/en/research/ · site: https://naive.ai/en/ · code: https://github.com/NaiveAI-Labs/Naive-N0.5-Flash
  - No separate hosted signup on those pages. The release is the open weights.

- @steipete (Peter Steinberger 🦞), Oct 1, 2026 4:52pm CT. Peter Steinberger flags Cloudflare’s new decision models, Clef and Clef-flash, and how fast the idea is spreading. https://x.com/steipete/status/2105778011635400949

  **Access:**

  - Weights: https://huggingface.co/Cloudflare/clef · https://huggingface.co/Cloudflare/clef-flash
  - Announcement linked from the post: https://blog.cloudflare.com/clef-decision-models/
  - Workers AI docs: https://developers.cloudflare.com/workers-ai/models/clef/ · https://developers.cloudflare.com/workers-ai/models/clef-flash/

- @OpenRouter (OpenRouter), Sep 23, 2026 9:49am CT. OpenRouter lists Space Bunny Alpha, a stealth flash model with 1M context, adjustable reasoning, and text, image, and video input. https://x.com/OpenRouter/status/2102772427105407270

  **Access:**

  - Hosted: https://openrouter.ai/stealth/space-bunny-alpha (linked from the post)
  - Hugging Face: https://huggingface.co/stealth-model/space-bunny-alpha is a placeholder. The repo has a README and no weight files. The card says GGUFs come once weights exist.

Also in this topic:

- @opencode, Sep 23, 2026 9:31am CT. OpenCode notes the stealth Space Bunny model is free for a week: 1M context, multimodal, zero data retention. https://x.com/opencode/status/2102767716666941864

  **Access:**

  - OpenCode Zen lists `space-bunny-free`: https://opencode.ai/docs/zen/
  - Same stealth model as the OpenRouter listing: https://openrouter.ai/stealth/space-bunny-alpha
  - Hugging Face: no public weights. See the placeholder above.

- @Rysana, Sep 29, 2026 10:04am CT. Rysana announces V2 with a speed and efficiency claim and little technical detail in the post. https://x.com/Rysana/status/2104950406589898811

  **Access:**

  - Site, with a “Get access” form: https://rysana.com/ · login: https://rysana.com/login
  - Hugging Face: no public weights. A search for `Rysana` returned none.

## Speech and audio models

**4 bookmarks.** Four bookmarks from the same day cover a full audio stack: controllable TTS, a cheaper Qwen ASR/TTS lineup, speaker diarization when people talk over each other, and a streaming ASR meant to run forever without drifting.

Representative posts:

- @Alibaba_Qwen (Qwen), Sep 23, 2026 4:11am CT. Qwen ships an audio stack (ASR, TTS, realtime, plus ASR-Next and TTS-Next) with large API price cuts. https://x.com/Alibaba_Qwen/status/2102687258990026993

  **Access:**

  - Hugging Face: no Qwen-Audio-3.1 weights. Searches for `ASR-Next` and `TTS-Next` under Qwen returned none.
  - Pages linked from the post: https://www.qwencloud.com/models/qwen-audio-3.1-asr-flash-filetrans · https://www.qwencloud.com/models/qwen-audio-3.1-realtime-plus
  - Also live: https://www.qwencloud.com/models/qwen-audio-3.1-asr-flash · https://www.qwencloud.com/models/qwen-audio-3.1-asr-flash-streaming
  - ASR-Next, TTS, and TTS-Next: no public model page. The obvious `qwencloud.com` slugs 404, and the post says more APIs are coming soon.
  - Speech docs: https://docs.qwencloud.com/developer-guides/speech/speech-to-text-models · getting started: https://docs.qwencloud.com/developer-guides/getting-started/introduction

- @FishAudio (Fish Audio), Sep 23, 2026 12:01pm CT. Fish Audio’s Drama 3 preview: controllable TTS where tone, pace, and character are plain language, including mid-sentence voice shifts. https://x.com/FishAudio/status/2102805658005635294

  **Access:**

  - Hugging Face: no Drama 3 repo. The fishaudio org lists S2-Pro, S1-mini, and older Fish Speech models, not Drama 3.
  - Signup: https://fish.audio/auth/signup/ · API keys: https://docs.fish.audio/developer-guide/getting-started/api-key
  - Public TTS docs do not list Drama 3. The model enum there is `s1`, `s2-pro`, `s2.1-pro`, and `s2.1-pro-free`: https://docs.fish.audio/api-reference/endpoint/openapi-v1/text-to-speech
  - The post says to comment DRAMA for a preview key. No separate waitlist URL.

- @SamuelZengML (Samuel Zeng), Sep 23, 2026 6:48am CT. Audio8 ASR Infinite is an open streaming speech model meant to transcribe indefinitely at low latency without drift. https://x.com/SamuelZengML/status/2102726739449332221

  **Access:**

  - Weights: https://huggingface.co/Edge0/Audio8-ASR-Infinite
  - No separate hosted API on the card. It is a local streaming checkpoint.

Also in this topic:

- @NVIDIAAI, Sep 23, 2026 10:02am CT. NVIDIA’s Nemotron 3 Diarization model (100M) labels who spoke when for up to eight speakers, including overlap, on Hugging Face. https://x.com/NVIDIAAI/status/2102775666366435450

  **Access:**

  - Weights: https://huggingface.co/nvidia/Nemotron-3-Diarization
  - Writeup: https://huggingface.co/blog/nvidia/nemotron-diarization · demo space: https://huggingface.co/spaces/nvidia/nemotron-diarization
  - No separate NVIDIA API signup on the card. The card loads the checkpoint from Hugging Face.

## Agent harnesses, sandboxes, and Jev

**5 bookmarks.** These are about the machinery around a model rather than the model weights. Monty is a millisecond Python sandbox for agents that write code. The Cursor note is a long prompt for cutting harness token cost per finished task. Two posts are specifically about Jev: an architecture teardown that promises open weights, and CLM-8B as a faster system-1 that claims to beat Jev on long coding benches. Hermes Desktop-in-a-browser is the UI piece.

Representative posts:

- @ericzakariasson (eric zakariasson), Sep 23, 2026 3:12pm CT. A Cursor engineer posts a long prompt for cutting an agent harness’s price-weighted token cost per finished task without dropping quality. https://x.com/ericzakariasson/status/2102853511637774551
- @samuelcolvin (Samuel Colvin), Sep 25, 2026 7:59am CT. Pydantic’s Samuel Colvin releases Monty, an open-source Python sandbox that starts in about a millisecond and can dump and resume. https://x.com/samuelcolvin/status/2103469459981619243
- @jackyk02 (Jacky Kwok), Sep 23, 2026 6:37pm CT. Jacky Kwok’s Contrastive Language Model (CLM-8B) is a fast system-1 for computer use, games, and tools, benchmarked against Jev and ahead on long-horizon coding. https://x.com/jackyk02/status/2102905335925424285

  **Access:**

  - Weights: https://huggingface.co/Contrastive-LM/CLM-v0.1-8B · org: https://huggingface.co/Contrastive-LM
  - Code: https://github.com/Contrastive-LM/CLM · blog: https://contrastive-lm.notion.site
  - No hosted API in the post. The release is the open checkpoint.

- @4rcherhume (Archer), Sep 17, 2026 7:00am CT. Archer publishes a writeup of Jev’s architecture and says an open-weight version is coming once training finishes. https://x.com/4rcherhume/status/2100555442061820286

  **Access:**

  - Hugging Face: no official Jev weights. The post says an open-weight version is still training. A `Jev` search returns community repos, not a TypeSafe card.
  - Vendor docs: https://docs.typesafe.ai/introduction · models: https://docs.typesafe.ai/models · API: https://docs.typesafe.ai/api · keys: https://docs.typesafe.ai/introduction/quickstart
  - Console: https://console.typesafe.ai · announcement: https://typesafe.ai/blog/introducing-system-one-models-and-jev
  - Architecture note linked from the post: https://archerhume.com/posts/jevs-architecture-unmasked/?v=3

Also in this topic:

- @BearHuddleston, Sep 27, 2026 2:22am CT. A Nous Research PR so `hermes webapp` serves the real Hermes Desktop (chat, files, git, a refresh-safe terminal) in any browser. https://x.com/BearHuddleston/status/2104109388780744775

## Agents that build things

**3 bookmarks.** taiga-s1 is a tiny local policy that drives FreeCAD. GameDev OS is a skill pack that turns a coding agent into a nine-role game studio. Xiaomi’s RL environment dump is a published task set.

Representative posts:

- @sxhivs (shiv), Sep 27, 2026 12:45pm CT. A 1.2M-param local “system-1” model, taiga-s1, is supposed to click through FreeCAD and build 3D parts in about a millisecond per decision. https://x.com/sxhivs/status/2104266076469236040

  **Access:**

  - Weights: https://huggingface.co/shhivv/taiga-s1
  - No hosted API on the card. It is a tiny local checkpoint.
- @emmanuel_2m (Emm | scenario.com), Sep 24, 2026 7:19am CT. Scenario open-sources GameDev OS: nine specialist roles and 64 skills so a coding agent can run a small game studio. https://x.com/emmanuel_2m/status/2103097017073361137
- @HarveenChadha (Harveen Singh Chadha), Sep 26, 2026 2:24am CT. Xiaomi open-sourced an RL environments / tasks repo (MiMo-V2.6). https://x.com/HarveenChadha/status/2103747414775804223

## LLM as the recommender

**1 bookmarks.** One long post on Netflix retiring a decade of hand-built ranking features for GenRec, which turns watch history into text and lets a foundation model rank from that.

Representative posts:

- @thesupermannx (Superman), Sep 28, 2026 9:30am CT. A writeup of Netflix replacing a hand-built recommender with GenRec, an LLM ranker that reads watch history as plain language. https://x.com/thesupermannx/status/2104579598105379159

## High-RAM local workstation

**1 bookmarks.** Framework’s 192GB desktop pre-order. AMD Ryzen AI Max+ Pro 495, an open PCIe slot, Fedora as an option.

Representative posts:

- @FrameworkPuter (Framework), Sep 28, 2026 11:07am CT. Framework opens pre-orders for a 192GB Desktop with Ryzen AI Max+ Pro 495, an open x4 PCIe slot, and an optional Fedora config. https://x.com/FrameworkPuter/status/2104604039845752868

## Linux face login on the XPS

**1 bookmarks.** A one-off reply, not an AI post. The Dell XPS camera has an IR sensor, and Howdy can use it for face login and audio commands.

Representative posts:

- @mwhuss (Marshall Huss), Sep 13, 2026 1:54pm CT. The Dell XPS camera’s IR sensor can do face login via Howdy, in a reply about that machine. https://x.com/mwhuss/status/2099210237647753615

## Every bookmark

| # | Author | Posted (CT) | Topic | Post |
|---|---|---|---|---|
| 1 | @Oluwaphilemon1 | Oct 1, 2026 9:32pm CT | Consumer-GPU inference speed | [2105848435672764747](https://x.com/Oluwaphilemon1/status/2105848435672764747) |
| 2 | @thepirateface | Sep 30, 2026 9:26am CT | Refusal-reduced weights and rehosting | [2105303200744292718](https://x.com/thepirateface/status/2105303200744292718) |
| 3 | @steipete | Oct 1, 2026 4:52pm CT | New model launches | [2105778011635400949](https://x.com/steipete/status/2105778011635400949) |
| 4 | @AntLingAGI | Sep 30, 2026 11:33am CT | New model launches | [2105335205741596911](https://x.com/AntLingAGI/status/2105335205741596911) |
| 5 | @coldniko | Sep 29, 2026 3:00pm CT | Consumer-GPU inference speed | [2105024852742787195](https://x.com/coldniko/status/2105024852742787195) |
| 6 | @Rysana | Sep 29, 2026 10:04am CT | New model launches | [2104950406589898811](https://x.com/Rysana/status/2104950406589898811) |
| 7 | @sxhivs | Sep 27, 2026 12:45pm CT | Agents that build things | [2104266076469236040](https://x.com/sxhivs/status/2104266076469236040) |
| 8 | @thesupermannx | Sep 28, 2026 9:30am CT | LLM as the recommender | [2104579598105379159](https://x.com/thesupermannx/status/2104579598105379159) |
| 9 | @FrameworkPuter | Sep 28, 2026 11:07am CT | High-RAM local workstation | [2104604039845752868](https://x.com/FrameworkPuter/status/2104604039845752868) |
| 10 | @BearHuddleston | Sep 27, 2026 2:22am CT | Agent harnesses, sandboxes, and Jev | [2104109388780744775](https://x.com/BearHuddleston/status/2104109388780744775) |
| 11 | @naiveailab | Sep 27, 2026 11:29am CT | New model launches | [2104247060186951725](https://x.com/naiveailab/status/2104247060186951725) |
| 12 | @coldniko | Sep 28, 2026 1:08am CT | Consumer-GPU inference speed | [2104453283255287915](https://x.com/coldniko/status/2104453283255287915) |
| 13 | @Beamsters1 | Sep 27, 2026 4:15am CT | Extreme compression for local Qwen | [2104137834013892803](https://x.com/Beamsters1/status/2104137834013892803) |
| 14 | @HarveenChadha | Sep 26, 2026 2:24am CT | Agents that build things | [2103747414775804223](https://x.com/HarveenChadha/status/2103747414775804223) |
| 15 | @ashxhart | Sep 25, 2026 7:31pm CT | Consumer-GPU inference speed | [2103643602937114924](https://x.com/ashxhart/status/2103643602937114924) |
| 16 | @TeksEdge | Sep 25, 2026 11:13am CT | Refusal-reduced weights and rehosting | [2103518301238485073](https://x.com/TeksEdge/status/2103518301238485073) |
| 17 | @samuelcolvin | Sep 25, 2026 7:59am CT | Agent harnesses, sandboxes, and Jev | [2103469459981619243](https://x.com/samuelcolvin/status/2103469459981619243) |
| 18 | @TeksEdge | Sep 24, 2026 3:00pm CT | Extreme compression for local Qwen | [2103212883857543441](https://x.com/TeksEdge/status/2103212883857543441) |
| 19 | @xiangxiang103 | Sep 25, 2026 6:05am CT | Refusal-reduced weights and rehosting | [2103440630257270932](https://x.com/xiangxiang103/status/2103440630257270932) |
| 20 | @OrcaRouter | Sep 24, 2026 10:29am CT | Extreme compression for local Qwen | [2103144808412037578](https://x.com/OrcaRouter/status/2103144808412037578) |
| 21 | @emmanuel_2m | Sep 24, 2026 7:19am CT | Agents that build things | [2103097017073361137](https://x.com/emmanuel_2m/status/2103097017073361137) |
| 22 | @PrismML | Sep 17, 2026 4:03pm CT | Extreme compression for local Qwen | [2100692248480596348](https://x.com/PrismML/status/2100692248480596348) |
| 23 | @sudoingX | Sep 24, 2026 8:00am CT | Extreme compression for local Qwen | [2103107193016844653](https://x.com/sudoingX/status/2103107193016844653) |
| 24 | @OpenRouter | Sep 23, 2026 9:49am CT | New model launches | [2102772427105407270](https://x.com/OpenRouter/status/2102772427105407270) |
| 25 | @FishAudio | Sep 23, 2026 12:01pm CT | Speech and audio models | [2102805658005635294](https://x.com/FishAudio/status/2102805658005635294) |
| 26 | @Alibaba_Qwen | Sep 23, 2026 4:11am CT | Speech and audio models | [2102687258990026993](https://x.com/Alibaba_Qwen/status/2102687258990026993) |
| 27 | @jackyk02 | Sep 23, 2026 6:37pm CT | Agent harnesses, sandboxes, and Jev | [2102905335925424285](https://x.com/jackyk02/status/2102905335925424285) |
| 28 | @ericzakariasson | Sep 23, 2026 3:12pm CT | Agent harnesses, sandboxes, and Jev | [2102853511637774551](https://x.com/ericzakariasson/status/2102853511637774551) |
| 29 | @NVIDIAAI | Sep 23, 2026 10:02am CT | Speech and audio models | [2102775666366435450](https://x.com/NVIDIAAI/status/2102775666366435450) |
| 30 | @SamuelZengML | Sep 23, 2026 6:48am CT | Speech and audio models | [2102726739449332221](https://x.com/SamuelZengML/status/2102726739449332221) |
| 31 | @opencode | Sep 23, 2026 9:31am CT | New model launches | [2102767716666941864](https://x.com/opencode/status/2102767716666941864) |
| 32 | @studio_yebisu | Sep 18, 2026 5:18pm CT | Extreme compression for local Qwen | [2101073385744724378](https://x.com/studio_yebisu/status/2101073385744724378) |
| 33 | @4rcherhume | Sep 17, 2026 7:00am CT | Agent harnesses, sandboxes, and Jev | [2100555442061820286](https://x.com/4rcherhume/status/2100555442061820286) |
| 34 | @0xSero | Sep 17, 2026 5:06pm CT | Extreme compression for local Qwen | [2100708075325841839](https://x.com/0xSero/status/2100708075325841839) |
| 35 | @mwhuss | Sep 13, 2026 1:54pm CT | Linux face login on the XPS | [2099210237647753615](https://x.com/mwhuss/status/2099210237647753615) |
