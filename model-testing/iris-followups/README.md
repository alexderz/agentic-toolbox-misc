# Iris follow-ups

[Iris](../../iris/) reads Alex's X bookmarks and files research notes. Model Master, the agent that runs
Alex's local model lab (an RTX 3090 and a V100 in a box called Titan), reads each note and follows it up:

- **Models**: check the weights, work out whether and how they fit, download them, and run at least a
  viability test (fit, tokens per second, time to first token, long-context retrieval, a short quality check,
  then whatever the model claims to be good at). New quants of models we already run get the standard
  speed and quality comparison against the quants we have. Full results go to
  [agentic-model-testing](https://github.com/alexderz/agentic-model-testing).
- **Tech to try**: find the real upstream, explain how it works, and work out what it would take to run it
  here, what it would improve, and what it would cost. Nothing gets installed from a bookmark alone.
- **Tech updates**: new engine releases get qualified against the build we run, and adopted when they win.

One file per Iris note day, appended as runs land and as test results come in.

| Follow-up | Covers |
|-----------|--------|
| [2026-11-09](2026-11-09-followup.md) | OrcaCyber ERNIE 5.5 Flash Base abliterated (tested: fits, too slow to read prompts, base model; not useful here); Stag (no value) |
| [2026-11-10](2026-11-10-followup.md) | TwIL-8B (tested: balanced variant fast and correct, verbose overthinks); RustingStrata (tested: works, 3.5x slower than Strata, not adopted); TensorFold 1.2.7 (qualify next); BeeLlama SINQ, NInfer (watch); Browser Use 1.0, T3 Code MCP; Keep-an-eye tracker baseline |
| [2026-11-11](2026-11-11-followup.md) | Unsloth Dynamic V3.1 Qwen3.8-27B (tested: no difference shown); Nex-N2.6 (tested: fits, too slow to prefill for agents) |
| [2026-11-12](2026-11-12-followup.md) | Post on Chinese labs distilling frontier models (news, no action); MACaQ-R Qwen3.6-35B-A3B (tested: no difference vs its Unsloth parent on our checks; KL-divergence check next), MACaQ toolkit (watch); checkpoint-forensics post (news); Perplexity pplx-decider v1.3 (flash downloaded, bench built; 27B does not fit) |
| [2026-11-13](2026-11-13-followup.md) | T3 Tots v1.4.34 (watch: unofficial T3 Code companion, not installed; handed to the T3 Code owner) |

— Hermius Maximus @alexderz
