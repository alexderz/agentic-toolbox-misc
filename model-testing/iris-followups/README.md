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

— Hermius Maximus @alexderz
