# Hyperframes Composition Brief: AMS2 — Ant vs Bee Championship

## Objective
Create a short launch-style brag video for the AMS2 Ant vs Bee Championship race-control dashboard.

## Output
- Composition directory: `brag-output/composition/`
- Rendered video: `brag-output/brag.mp4`
- Format: landscape — 1920x1080
- Duration: 20s

## Source Material
- Project root: `/home/user/simtrack`
- Primary files read: `index.html` (single-file app — markup, inline `:root` CSS vars, and the `raceData` array)
- Product name: AMS2 — Ant vs Bee Championship
- Tagline / strongest claim: a 20-round, two-driver championship with full F1-style session formats and points
- Key UI to recreate: the rivalry panel (ANT 00 / BEE 00), the Round 01 hero card, the season calendar table with format tags, and the click-to-open track intel drawer
- Copy that must appear verbatim:
  - `ANT` / `BEE` / `00`
  - `Next Event: Round 01` · `Adelaide` · `Porsche 911 • The Season Opener`
  - `Practice 20M` / `Qualifying 10M` / `Race 30M`
  - `Season Calendar` · `Click race for track intel`
  - `Spa Historic 1970` · `14.12km` · `20` · `Historical` · `Twice as long as modern Spa.`
  - `Fastest Lap: +1 Point`
  - `Season 1.0` · `Pre-season build`

Note: the live URL (bgs123123.github.io/simtrack/) and the page's Tailwind/Lucide CDNs are blocked by this
environment's egress policy, so the UI is **recreated in hand-written CSS from the project source** rather than
screen-captured. All colors, fonts, copy and layout are taken from `index.html`. This also keeps the render
deterministic (no network at render time), which the Hyperframes determinism rules prefer.

## Creative Direction
- Tone preset: `cinematic`
- Creative direction: F1 broadcast season-launch title sequence
- Interpretation: Big italic caps, full-bleed panels, dramatic reveals over quick cuts. Each line lands before the next. Restraint is the joke — nothing winks at the camera, because the site doesn't either.
- Angle: Full F1 broadcast treatment applied to a grudge match between two mates. Everything on the site is real and serious — 20 circuits, real session formats, a real points system — and it exists to settle one argument. The scoreline is 00–00: everything is still to play for.
- Hook: the two huge mono zeros — "TWENTY ROUNDS. TWO DRIVERS. NOTHING SCORED YET."
- Outro / punchline: AMS2 mark → ANT vs BEE → "LIGHTS OUT SOON."
- Avoid:
  - Generic SaaS language
  - Abstract filler visuals
  - Unrelated visual redesign
  - Engine noise / crowd / racing-game trailer clichés

## Visual Identity
- Background: `#050505` · Surface: `#0f0f0f` · Border: `#1f1f1f`
- Text: `#f0f0f0` · Muted: `#737373`
- Accent: `#ff3e3e` (brand red), UI red-600 `#dc2626`
- Format tags: F1 `#ef4444` · GT3 `#22d3ee` · ENDUR `#eab308` · SPRNT `#a855f7`
- Display font: Inter 900 italic, uppercase, tight tracking (vendored woff2)
- Body/number font: JetBrains Mono 700 (vendored woff2)
- Visual references: red left-border hero card, hairline `#1f1f1f` rules, pill-shaped format tags, pulsing red live dot

## Storyboard
Use the storyboard in `brag-output/brag-plan.md` as the creative contract.

Scene summary (refined timing — Hyperframes owns exact values):
1. Rivalry / the zeros — 0.0–3.5s — ANT 00 over BEE 00, hook line
2. Round 01: Adelaide — 3.5–7.5s — hero card, 20/10/30 session split counting up
3. Season calendar — 7.5–11.5s — rows streaming in with format tags, list scrolls to show scale
4. Track intel — 11.5–15.5s — cursor clicks Spa Historic 1970, drawer opens, 4 fields land
5. Points grid — 15.5–17.02s — P1 25 … P5 10, "Fastest Lap: +1 Point"
6. Outro slam — 17.02–20.0s — AMS2 → ANT vs BEE → LIGHTS OUT SOON.

## Audio
- Audio role: cinematic support — a driving bed that builds
- Audio arc: held-breath open → lift on the season card → momentum through the calendar → tactile on the click → peak on the logo slam → hard cut
- Music: `assets/music/happy-beats-business-moves-vol-1-by-ende-dot-app.mp3` (120.19 BPM)
- Music treatment: `data-volume` 0.34, fade up over the first 0.6s, fade out over the last 0.35s
- Music cue guidance: bundled preset at `assets/music/cues/happy-beats-business-moves-vol-1-by-ende-dot-app.music-cues.json`. Strong cues used: **17.02s** (logo slam, locked) and **18.52s** (final line, locked). Beat grid 0.5s from 3.02s for sequential reveals.
- Audio-reactive treatment: subtle — bass drives the red accent glow and hero-card presence; overall energy nudges the background vignette. No waveform/equalizer visuals. Data pre-extracted to `assets/music/audio-bands.js` (30fps, 602 frames) with `hyperframes-creative/scripts/extract-audio-data.py`.
- Audio-coupled moments:
  - Scene 1 zeros settling — dry tick per zero
  - Scene 2 session stats — tick per stat as its number lands
  - Scene 3 calendar rows — soft click per row, dropping in volume as they accelerate
  - Scene 4 cursor press + drawer slide — click, then card-slide under the expand
  - Scene 6 AMS2 slam — single deep bell
- SFX selection guidance: repeated ticks use low-HF-risk files only (`interface/click_003`, `ui/click2`); the bell is reserved for the one logo payoff.
- SFX analysis guidance: `~/.claude/skills/brag/assets/sfx/sfx-analysis.md` — low HF risk for repeated/polished moments.
- Exact SFX choice: chosen after the animation existed (see composition `<audio>` elements).
- Audio files: copied into `brag-output/composition/assets/`

## Hyperframes Instructions
Built with the `hyperframes-core` contract (single paused GSAP timeline registered on `window.__timelines`, `data-*` timing, deterministic rules), `hyperframes-animation` motion, `hyperframes-creative` audio-reactive sampling, and `hyperframes-cli` for `check` + `render`. GSAP and both fonts are vendored locally under `assets/` because the jsDelivr and Tailwind CDNs are blocked in this environment — this also satisfies the `font_family_without_font_face` lint rule and keeps renders network-free.

Requirements met:
- Real UI, copy and colors from the source project throughout.
- All text held above the reading-time floor (short label ≥0.8s settled, sentence ≥0.3s/word).
- 20s total, within the 15–25s window.
- Music + 7 SFX files, audio-reactive treatment present.
- `hyperframes check` is the gate before render.
