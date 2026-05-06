# Zork I — v3: Multimedia (FROZEN)

This is a **frozen published snapshot** of Zork I. New work does NOT happen here.

| | |
|---|---|
| Repo | `Johnesco/zork1-v3` |
| Hub registration | `zork1-v3` (`versionOf: zork1`, `versionLabel: v3 — Multimedia`) |
| Companion repos | `zork1` (Current), `zork1-v0` (ZIL), `zork1-v1`, `zork1-v2` |
| Golden seed | **26** (in `tests/seeds.conf`) |
| Binary | `zork1-v3.ulx` (compiled from this repo's `story.ni`; packaged with audio into `.gblorb` at deploy time) |

## What v3 is

Where Zork intentionally diverges from ZIL-faithful behavior and starts leaning into what Inform 7 does best. v1 and v2 are bound to the original; v3 and beyond are not.

v3 adds two major enhancements while keeping any added text sparse to match the original style:

1. **Native Glk Sound** — zone-based ambient music + 16 SFX, driven from `story.ni` via Glk sound channels, bundled into `.gblorb` and played by Parchment's Emglken WASM engine. Auto-detected via `glk_gestalt(gestalt_Sound, 0)`; `SOUND ON` / `SOUND OFF` available in-game.

2. **CSS Atmospheric Effects** — mood palette zones with smooth color transitions, reversed status bar, CRT intro, Up-a-Tree leaves, egg-flash on the jewel-encrusted egg. Applied in this repo's `play.html` (always active for v3) and gated on `body.zork1-enhanced` in the shared IF Hub player.

## Editing rules

**Default:** Don't edit this repo. Work happens in **`Johnesco/zork1`** (Current).

This repo is only edited when:
- A v3-specific bug surfaces (e.g. mood palette glitch, sound mapping)
- A bug fix or enhancement from a lower version must be propagated up to here

If you patch this repo:
1. Edit `story.ni` here
2. Recompile: `python /c/code/ifhub/tools/pipeline.py zork1-v3 compile`
3. Run walkthrough with golden seed 26: `python /c/code/ifhub/tools/testing/run_walkthrough.py --config tests/project.conf --seed 26`
4. Commit + push (auto-deploys to `johnesco.github.io/zork1-v3/`)
5. Apply the same change to `zork1` (Current) if applicable

For the full multi-version workflow, see `C:\code\ifhub\reference\multi-version-guide.md`.

## Project-wide context

For Zork-specific game systems, scoring, multimedia details, and project workflow conventions, see the main repo's `CLAUDE.md` at `C:\code\text-games\i7\zork1\CLAUDE.md`.
