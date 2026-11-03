# @Steady_Alex bookmark scan, Oct 24 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Sat Oct 24, 2026 ~9:20am CT. Baseline: [Oct 23 delta](2026-10-23-steady-alex-bookmarks.md) (101 total, newest filed id 2113002020567453798).

## Summary

- **New vs baseline:** 3 ids (newest 15 bookmarks read; the 4th onward were already filed).
- **Total:** 104 if no baseline ids were removed (full list not re-paged this run).
- **Memes skipped:** none new.
- **Folders:** no new folders (Keep an eye on this, Moodils, Cool tech to try, Memes, Cyber). Keep an eye on this +2 (Goose, Dessa launch post); Moodils +1 (Dessa, @jack post).

## Keep an eye on this

### Goose programming language (aardappel/goose)

@wvo (Wouter van Oortmerssen), posted Oct 23 1:10pm CT, replying to @ID_AA_Carmack's Oct 23 11:53am CT post about stack-only memory management in C/C++. Post text: made a language with "as many address-space-reserved huge stacks as the program statically needs, with bump alloc, stable pointers, all compile time safe and yet way faster than what you can do in C++/Rust".
https://x.com/wvo/status/2113694480650166428

- **What it is:** memory-safe systems language with no heap allocator, garbage collector, reference counting, destructors, or lifetime annotations. Dynamic values live inline on compiler-managed data stacks; scope exit frees memory. C/Rust-like syntax. Compiles to one C file; calls C via `extern fn`; bundled TinyCC backend compiles and runs a program in-process. Share-nothing worker threads that pass flat values over typed queues.
- **README benchmark claims (repo's own suite, 16 benchmarks):** 3.3x idiomatic C++ speed, 1.16x hand-optimized C++, 1.12x best safe Rust; 1.9x / 1.3x / 1.2x less memory respectively.
- **License:** Apache-2.0.
- **Release:** repo created Aug 30 2026 (4:10pm CT); releases v2026.1 (Oct 14 5:07pm CT), v2026.2 (Oct 15 9:40pm CT), v2026.3 (Oct 21 12:39am CT); last push Oct 22 8:50pm CT. ~1,450 GitHub stars at time of scan.
- **Requirements:** a C compiler (or the bundled TinyCC backend).

**Links:**

- GitHub: https://github.com/aardappel/goose
- Tutorial: https://github.com/aardappel/goose/blob/master/docs/tutorial.md
- Benchmarks: https://github.com/aardappel/goose/blob/master/bench/results.md
- Releases: https://github.com/aardappel/goose/releases
- Carmack post replied to: https://x.com/ID_AA_Carmack/status/2113675158154027495

### Dessa — Block's full-duplex speech-to-speech model (launch post)

@RagavanThurair (Ragavan Thurairatnam, Dessa lead), posted Oct 23 11:38am CT. Post text: first AI model you can have a realistic conversation with trained entirely on speech; full-duplex speech-to-speech; runs on consumer GPUs. Follow-ups same day: blog link (11:41am CT), safety-researcher invitation (12:59pm CT), world-knowledge/reasoning game demo (1:51pm CT).
https://x.com/RagavanThurair/status/2113671324400861645

Details under the Moodils entry below.

## Moodils

### Dessa — Block's full-duplex speech-to-speech model (@jack post)

@jack (Jack Dorsey), posted Oct 23 1:23pm CT. Post text: Dessa, "the most authentic full-duplex speech model ever built"; links block.xyz/dessa.
https://x.com/jack/status/2113697902916751661

- **What it is (per block.xyz/dessa):** research preview of a speech-to-speech model trained from scratch only on human conversational audio (no text, no pretrained models). Full-duplex (listens and speaks at once), does backchanneling and interruptions, carries emotion/laughter/sarcasm. Inference faster than real time.
- **Hardware (per page):** runs locally on a MacBook Pro M4 Max or better; launch post says consumer GPUs. Trained on one NVIDIA GB200 NVL72.
- **Availability:** no public weights, code, API, or signup found. HF search for "dessa" and GitHub search under `block` returned no Dessa repos at time of scan. Page offers early access to a small group of AI safety researchers via contact email on the page.
- **License:** none published.
- **Release:** small AI research lab at Block (founded by former members of the Toronto startup Dessa), lead Ragavan Thurairatnam; announced Oct 23 2026.

**Links:**

- Official page: https://block.xyz/dessa
- Launch post: https://x.com/RagavanThurair/status/2113671324400861645
- Safety-researcher invite post: https://x.com/RagavanThurair/status/2113691903866872251
- Reasoning/game demo post: https://x.com/RagavanThurair/status/2113704911749911028
