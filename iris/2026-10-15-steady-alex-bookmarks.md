# @Steady_Alex bookmark scan, Oct 15 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Thu Oct 15, 2026 ~9:15am CT. Baseline: [Oct 14 delta](2026-10-14-steady-alex-bookmarks.md) (79 total) on main.

## Summary

- **Total bookmarks:** 81 (one page, `result_count` 81, no `next_token`, page size 100).
- **New vs Oct 14 baseline:** 2 ids. All 79 baseline ids still present.
- **Memes skipped:** none new (Memes folder still holds 2108663800102609008 and 2107021822155985254).
- **Folders:** no new folders. Keep an eye on this now has 7; Moodils 16; Cool tech to try 14; Cyber 2; Memes 2 (Memes, Moodils, Cool tech to try, Keep an eye on this, Cyber).

## Keep an eye on this

### Jev 1.14 — TypeSafe System One decision model on OpenRouter

@OpenRouter, posted Oct 14 7:16pm CT. OpenRouter lists **TypeSafe: Jev 1.14** (`typesafe/jev-1.14`) as live. TypeSafe’s Oct 14 2026 blog names the release **jev-1.14.0**: structured decision / System One model (typed answers with calibrated probabilities — noul / choice / score; new `box` type on 1.14), not free-form chat. OpenRouter page: released Oct 14 2026; text + image input; structured decisions out; context 262K; $0.042/1M input, output free; provider TypeSafe; Decisions API (not chat completions). TypeSafe docs: model id `jev-1.14.0`; same $0.042/Mtok ($42/Btok) input, output free; default context 64k per-request / 32k per-question; long context raises both to 262k with header `TypeSafe-Danger-Zone-Long-Context: true`. Alias `jev-preview` → `jev-1.14.0`; as of the blog, `jev-latest` stays on `jev-1.13.0` for about a week then moves. Multimodal images and long context are gated on TypeSafe’s native API via danger-zone headers; OpenRouter’s model card lists text+images and 262K for the routed endpoint.
https://x.com/OpenRouter/status/2110525059093987468

**Access:**

- OpenRouter model page: https://openrouter.ai/typesafe/jev-1.14
- OpenRouter Decisions API: `POST https://openrouter.ai/api/alpha/decisions` · model `typesafe/jev-1.14` (alias `~typesafe/jev-latest`)
- OpenRouter Jev guide: https://openrouter.ai/docs/guides/community/jev
- OpenRouter multimodal decisions: https://openrouter.ai/docs/guides/community/multimodal-decisions
- TypeSafe blog (Oct 14 2026): https://typesafe.ai/blog/jev-1-14
- TypeSafe models docs: https://docs.typesafe.ai/models
- TypeSafe native API: `POST https://api.typesafe.ai/v1/systemone` · model `jev-1.14.0` / `jev-preview`
- TypeSafe console / signup: https://console.typesafe.ai/home
- OpenRouter signup / API keys: https://openrouter.ai/ · https://openrouter.ai/keys
- Product site: https://typesafe.ai/
- License / distribution: hosted SaaS (not an open-weight release). TypeSafe docs: not trained on customer requests/responses; ZDR available for enterprise (Legal / DPA on typesafe.ai).

### Ultramarine 1 Flash — Paper Instruments knowledge-work model (API now; weights later)

@bertgodel (Daanish Khazi, ceo @paperinstr), posted Oct 14 11:02am CT. Paper Instruments released **Ultramarine 1 Flash**: agentic model for professional knowledge work (finance, law, consulting, operations). Post-trained from open base **GLM-5.3 Flash** (Z.ai; HF card: ~320B total / ~18B active, natively multimodal) with large-scale non-verifiable RL; training table lists LoRA rank 64, context window 131,072, max agent turns 250. Technical report dated Oct 14 2026. X post: open-source intent, API available now, weights releasing in ~2 weeks; post-trained by a team of 5 for ~$300k all-in; claims similar performance to Fable 5 at ~60× lower cost. Product page: API pricing $0.15/1M input, $0.03/1M cached input, $0.50/1M output (same as GLM-5.3 Flash list); “Ultramarine on Hugging Face — Model weights coming soon.” Eval context for internal PI Knowledge Work suite noted as 262,144 tokens in the report notes.
https://x.com/bertgodel/status/2110400987622265232

**Access:**

- Product: https://www.paperinstruments.com/ultramarine
- Technical report / blog: https://www.paperinstruments.com/blog/ultramarine
- Docs quickstart: https://docs.paperinstruments.com/docs/ultramarine
- API base: `https://api.paperinstruments.com/v1` · model id `ultramarine-1-flash`
- Surfaces: OpenAI-compatible chat completions (`/v1/chat/completions`), Responses (`/v1/responses`), Anthropic-compatible Messages (`/v1/messages`)
- Console / billing / API keys: https://platform.paperinstruments.com
- Pricing (docs Billing): https://docs.paperinstruments.com/docs/ultramarine/billing — $0.15 / $0.03 cached / $0.50 per 1M tokens (output includes reasoning)
- Base model (open weights): https://huggingface.co/zai-org/GLM-5.3-Flash
- Ultramarine HF weights: not published yet (product page “coming soon”; X post ~2 weeks from Oct 14 2026)
- Company: https://www.paperinstruments.com/
- License / distribution: hosted API now; open-weight release stated as forthcoming (license for weights not published yet). Base GLM-5.3-Flash license is on its HF card.

## Skipped (Memes)

- None new. Memes folder unchanged: 2108663800102609008, 2107021822155985254.
