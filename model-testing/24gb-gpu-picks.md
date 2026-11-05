# Local models on one 24 GB GPU: picks from our grades (2026-11-03)

This note sits beside [agentic-model-testing](https://github.com/alexderz/agentic-model-testing).
That repository has the harness, the [method](https://github.com/alexderz/agentic-model-testing/blob/main/docs/model-research/method.md),
the model cards and the [standing picks](https://github.com/alexderz/agentic-model-testing/blob/main/docs/model-research/conclusions.md).
This note is the short version for someone setting up one card, and it uses grades newer than that repository's
last refresh (2026-10-27).

The question it answers: on a 24 GB card with about 128 GB of system RAM, which model and engine should you run
for coding agents? What we mean by good: long context, 20+ tokens per second per stream, several streams,
and prompt caches kept in RAM and on disk.

## Our rig and yours

- We test on one RTX 3090 (24 GB) with 125 GB of RAM.
- A 4090 with 128 GB fits everything below the same way. It decodes somewhat faster and reads prompts much faster.
- Speeds below are from the 3090.

## The grades

The agent core is 8 tests: t1 (a Python CLI), t2 (a Rust MCP server), t2t (the same server with a trust trap),
t3g and t3o (judging a known-good server and the model's own), and t4a-c (three bug-fix tickets).
A pass is graded by running the result, never by reading the model's own report.
The one-shots are scored 0-10 by hand from rendered frames. t5 is an animated SVG orrery, t6 a three.js voxel
pagoda in a single reply, and t7 a three-floor labyrinth generator built by an agent.

| Model, quant, engine | Agent core | t5 orrery | t6 pagoda | t7 labyrinth | Speed on the 3090 |
|---|---|---|---|---|---|
| Qwopus3.8-27B Coder Flash, EXL3 5.0 bpw + own MTP, TabbyAPI, 98k | 8/8 | parses; gears clumped (first look) | complete, no floating parts (first look) | not run yet | 98-112 t/s decode, about 60 after 88k |
| Qwopus3.8-27B Coder Flash, Q4_K_M, llama.cpp | 8/8 | parses; gears clumped (first look) | complete (first look) | not run yet | 41-44 t/s decode, 27 after 88k |
| Qwen3.8-Flash-Next IQ3_S (unpruned), llama.cpp v0.7.0, experts in RAM, 212k | 8/8 | 7 | 10 | 10 | 17-19 t/s over most runs (21-23 streamed) |
| Qwen3.8-27B Defiance Uncensored IQ4_XS, llama.cpp, 192k | 8/8 | 0 (ran out of reply budget) | 7 | 10 | 24-32 t/s over most runs |
| OrcaSAQ-2-Cyber-27B, llama.cpp | 8/8 | 0 (broken SVG) | 0 (prose inside the HTML) | fail (timeout) | 46-62 t/s over most runs |
| Tiel-Coder-35B-A3B UD-IQ4_XS, llama.cpp, 262k | 7/8 | 2 | 0 (three.js API error) | fail | 60-98 t/s over a run |
| Swift 1.5 Flash-Next (pruned) IQ3_XXS, llama.cpp v0.7.0, 262k | 6/8 | 2 | 8 | fail (timeout) | 14-18 t/s over most runs |
| Gemma 4 26B-A4B, vLLM | 2/8 | 2 | 7 | fail | 85-200 t/s over a run |

Notes on the table:

- Every row is one round. Rounds 2-5 are planned, so treat a single pass or miss as a lead, not a verdict.
- Tiel's miss matters more than its score shows. On t3o its own server got 13 of 14 checks right, and it reported
  all 14 as correct.
- Swift 1.5 missed t2 on the 3-hour cap (the server built and answered with 9 tools, but its own tests did not
  finish). On t3o its own server failed 2 of its tests.
- Gemma 4 26B is fast and thin: its t2 server, its own t3o server and two of the bug fixes do not build, and it
  claimed DONE on a fix that failed the hidden tests.
- Qwopus one-shots have first-look notes only, not rubric scores yet.
- "Over a run" is output tokens per second across a whole agent run as the harness reports it, so it includes
  long prompts. It is lower than a decode benchmark. The t3 tests run subagents against one slot, so they run
  slower still (Flash-Next 6-10 t/s); "most runs" leaves those out.

## Is Qwopus a better coder than Tiel or plain Qwen3.8-27B?

- **Against plain Qwen3.8-27B: as good, and faster to finish.** On our quick set Qwopus tied stock at 26/28,
  and it matched it on long-context retrieval (3/3) and vision (3/3). It thinks about a third less on easy
  problems, so jobs finish sooner. On hard problems both think to the cap.
- **Against Tiel: Qwopus is the better coder; Tiel is the faster one.** Qwopus passed all 8 agent tests in both
  configurations we graded. Tiel passed 7 and overstated its own result on the one it missed. Tiel runs 2-3x faster
  per stream and holds 262k of context. Use Tiel where you check the work anyway, and Qwopus where the agent's
  own "done" has to be true.
- **Neither is a good one-shot artist.** Single-reply pagodas and orreries are weak across the 27B and 35B models.
  The best one-shots in this round came from Flash-Next.

## What to run

### Flash-Next: the smartest option

Two routes, depending on whether you want proven or fast.

**Proven: llama.cpp v0.7.0, Flash-Next IQ3_S unpruned, experts in RAM with a GPU cache.**
- It went 8/8 on the agent core and scored 10 on both the pagoda and the labyrinth, the best one-shot set of this round.
- It runs at about 17-19 t/s over a run (21-23 streamed), one stream at a time. That is under the 20 t/s
  target, and a second stream would make it slower.
- The official image is `ghcr.io/ggml-org/llama.cpp:server-cuda12-b11429`. We run it with:

```
-ngl 999 -cmoe --moe-cache-mib 9216 -c 211968 -ctk q8_0 -ctv q8_0 -b 2048 -ub 1024 -t 16 -fa on -lm none
--reasoning-budget 24000 --temp 1 --top-k 20 --top-p 0.95 --min-p 0
```

- `-lm none` loads the experts eagerly. Without it the first request stalls on page faults.

**Fast: Strata 0.2.x with the Gyro-S quant and Flash-Next's own MTP head.**
- It decodes 106-158 t/s with one stream and reads prompts at about 2,500 t/s.
- It found a planted fact in a 64k prompt.
- It passed t2 in full (6 tools, 108 tests) and scored 9/10 on the agent pagoda.
- The catch: that is one graded run on a beta engine. t1, t3 and t4 have not been run on it, and multi-stream
  speed is not measured.
- Strata can keep conversations in RAM (`--conversation-cache-mib`). Saving slots to disk is optional and off by default.
- Under rootless Podman, give the container `--cpus N`, not `--cpuset-cpus`. Without a delegated cpuset
  cgroup the container never starts and the server returns HTTP 500.

### Qwen3.8 27B: Qwopus

- **One fast stream:** Qwopus3.8-27B Coder Flash in EXL3 5.0 bpw with its own MTP head, on TabbyAPI.
  - 98k context with 8-bit KV and about 2.9 GB free at full context.
  - 98-112 t/s, about 60 after 88k of context.
  - It passed all 8 agent tests.
  - The 5.0 bpw quant is one we converted ourselves. 6.0 bpw with MTP fits only 57k, and Q6_K GGUF does not load at all.
  - TabbyAPI runs one stream (`max_batch_size 1` as we tested it) and does not save caches to disk.
- **Several streams, with RAM and disk caches:** Qwopus Q5_K_M (or Q4_K_M) on llama.cpp.
  - 98k fits with 8-bit KV.
  - 37-44 t/s for one stream, about 25 after 88k.
  - A dense 27B with no draft model will struggle to hold 20 t/s on each of two streams. Expect about
    20-25 each at short context, less as context grows. That is an estimate, not a measurement.

### Several streams at 20+ t/s each: Tiel-Coder-35B-A3B

- It is an MoE with 3B active parameters, so it is the only graded coder here with room for 3-4 streams above 20 t/s.
- One stream runs at 60-98 t/s over a run, and it holds 262k of context.
- The cost: 7/8, and the miss was a false claim of success. Check its work.
- Suggested llama.cpp flags. We graded it as one slot with f16 KV; the three slots and the caches are our
  suggestion, not a tested setup:

```
-c 262144 -np 3 --kv-unified -fa on -ngl 999 --cache-ram 16384 --slot-save-path /nvme/slots --jinja
--temp 0.6 --top-p 0.95 --top-k 20 --min-p 0
```

- `--cache-ram` keeps recent prompt caches in system RAM. `--slot-save-path` saves to disk only when you call the
  `/slots` API, so add a small script that saves idle slots and restores them.
- Run it at temperature 0.6. With other sampling an earlier 4-bit run called an endpoint that does not exist.

## What we have not measured yet

- **Multi-stream speed for any of these models.** Our only parallel run so far was DeepSeek. A new test 11 runs
  1, 4 and 8 parallel OpenCode judge sessions on one load and grades both the serving (every session finishes,
  20+ t/s per stream at 4) and the judging. Until it reports, every multi-stream number above is an estimate.
- **Writing.** A new core test 9 (a short story, then a self-edit) runs early in every model's round.
- **Rounds 2-5** for every row, and the held agent-with-browser test t8 for the Flash-Next and Defiance rows.

## Sources

- Agent and one-shot grades: our private bake-off runs of 2026-10-22 to 2026-11-03, graded on 2026-11-03.
  The public repository will carry them at its next refresh.
- Qwopus: our probe of 2026-11-01 (quick set, long context, vision, speed and fit by quant).
- Engines, flags and earlier picks: [agentic-model-testing docs/model-research](https://github.com/alexderz/agentic-model-testing/tree/main/docs/model-research),
  including the [Flash-Next](https://github.com/alexderz/agentic-model-testing/blob/main/docs/model-research/models/qwen3.8-flash-next.md),
  [Gyro-S](https://github.com/alexderz/agentic-model-testing/blob/main/docs/model-research/models/gyro-s-flash-next.md)
  and [Tiel](https://github.com/alexderz/agentic-model-testing/blob/main/docs/model-research/models/tiel-coder-35b.md) cards.
