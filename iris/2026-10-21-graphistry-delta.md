# Graphistry / Louie.ai follow-up delta — 2026-10-21

Baseline: [2026-10-07-graphistry-investigation-harnesses.md](2026-10-07-graphistry-investigation-harnesses.md). Checked Wed Oct 21 2026 ~9:55am CT.

## New: BSides Augusta 2026 training repo (public)

- Repo: https://github.com/graphistry/bsides-augusta-2026 (created 2026-10-20, last push 2026-10-21; no LICENSE file; ~142 KB).
- Title: "From AI Copilot to Commander — AI Agents and RAG for Security Automation and Investigation", two-day hands-on training, BSides Augusta 2026.
- Dates: Oct 21–22 2026, 09:00–17:00 ET, Georgia Cyber Center (Hull-McKnight building). Instructors Leo Meyerovich and Sindre Breda (Graphistry / Louie.ai). README says the BSides Canberra and BSides Las Vegas 2026 workshops were one-day versions of this course.
- Course frame: plan → run → eval. One incident throughout: BOTSv3 Incident B2 (AWS key compromise across email, CloudTrail, IAM, EC2) on a Splunk cyber range.
- Labs: Lab 0 setup (Splunk via MCP harness, `louie-py`, Louie desktop); Lab 1 local OSS LLM plus Laya (https://github.com/NandhaKishorM/laya), described as an open-source Jev-compatible decision model; Lab 2 AI CTF with BYO agent (Claude Code / OpenCode / Codex over Splunk MCP) or Louie; Lab 3 skills, timelining and evals; Lab 4 triage router and contamination checks; Capstone IR report plus graphs on Graphistry Hub.
- Talk titles include "Modern harnesses, thick MCPs & the semantic layer", "Evals in a SOC setting", "Securing agents (proxies, auto mode, monitors, MCP vs skills)".
- Requirements per README: laptop with 8 GB+ RAM, no GPU; free Graphistry Hub account (https://hub.graphistry.com); Splunk BOTSv3 range credentials given in-session. Louie desktop: https://download.louie.ai

## New: graphistry-skills graphistry-mcp skill (unreleased, Development section)

- Repo: https://github.com/graphistry/graphistry-skills (BSD-3-Clause). PR #33 merged 2026-10-14.
- Added a `graphistry-mcp` skill for driving a live Graphistry visualization session from an MCP client (Streamable HTTP, personal-key and JWT auth, nine-tool surface, GFQL as JSON wire format). Fixed: fix-and-retry loop on GFQL errors, reporting after three failed attempts; corrected row-cap rule.

## Unchanged

- Graphistry blog: no post newer than the Oct 9 GFQL indexes post seen on the last check (RSS fetch now returns a captcha redirect).
- Louie.ai /blog /news /changelog still 404.
- X: no @Graphistry or @LOUIE_AI posts since Oct 15; @lmeyerov Oct 18 posts off-topic.
- louie-py tip 2026-08-04; graphistry-mcp tip 2025-10-09; louie.ai-docs tip 2026-07-25. pygraphistry 0.61.1 released 2026-10-21 (GFQL fixes, off-topic).
