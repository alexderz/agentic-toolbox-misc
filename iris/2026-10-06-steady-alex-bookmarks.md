# @Steady_Alex bookmark scan, Oct 6 2026

Account: Alex D (@Steady_Alex), user id 2093905271701590017.
Pulled Tue Oct 6, 2026 ~9:25am CT. Baseline: [Oct 5 delta](2026-10-05-steady-alex-bookmarks.md) (47 total) on main.

## Summary

- **Total bookmarks:** 48 (one page, `result_count` 48, page size 100).
- **New vs Oct 5 baseline:** 1 id. All 47 baseline ids still present.
- **Memes skipped:** none new.
- **Folders:** one new folder, **Cool tech to try** (2107295758512796057), holding today's one new post. Moodils, Cyber, and Memes are unchanged.

## Agents that build things (Cool tech to try)

### Genex, a desktop app for building games with AI

@genex_games, posted Oct 5 11:39am CT. A free, MIT-licensed desktop studio that wraps existing coding agents in a game-dev harness. It currently targets Three.js browser games: describe a game, watch a live preview, and keep the project as ordinary local files that export as a static web bundle (or publish on genex.games). You pick separate models to plan, build, and judge; visual judges check the builders' output. Agents come from Claude Code (Claude subscription), Codex CLI (ChatGPT subscription), or local models through Ollama or Bonsai, so no API keys are needed. Tools include local Blender (modeling, rigging, GLB export) and Meshy (generated models). An experimental self-improvement loop (off by default) edits its own tools and prompts in git, snapshots before every change, has a blind judge compare results, and rolls back a version that won't start. First public release is 0.1.3: macOS Apple Silicon is supported, Linux x64 is a preview `.deb`/`.rpm` that pulls in `bubblewrap`, `socat`, and `ripgrep` for its agent sandbox (Ubuntu 24.04's sandbox restriction is listed as an open issue), and Windows plus Unity and Unreal plugins are still coming. The only paid part is optional asset generation through the Genex plugin, which needs a Genex account. Continues the Oct 3 "agents that build things" cluster (GameDev OS, Bonsai 2 building a game through Hermes agent, AgentCraft).
https://x.com/genex_games/status/2107148754633507237 · https://genex.games/desktop

**Access:**

- Source: https://github.com/genex-games/genex-desktop (MIT)
- Downloads: https://github.com/genex-games/genex-desktop/releases
- Product page and FAQ: https://genex.games/desktop
- Not a model, so no Hugging Face entry. A Genex account is needed only for asset credits and hosted publishing.
