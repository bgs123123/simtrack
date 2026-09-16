# Brag Plan: AMS2 — Ant vs Bee Championship

## What is this app?
A season-long race control dashboard for a two-driver Automobilista 2 championship — 20 rounds, four session formats, live points tracking — built for a rivalry between exactly two people: Ant and Bee.

## The angle
Full Formula 1 broadcast treatment applied to a grudge match between two mates. Every element on the site is real and serious — 20 real circuits, real lap formats, a real points system, track intel on every round — and it exists to settle one argument. The video plays it completely straight. The comedy and the charm are the same thing: this is a world championship with a grid of two.

The scoreline is currently 00–00. Nothing has happened yet. That is the most cinematic thing about it — everything is still to play for.

## Hook (first 2-3 seconds)
The rivalry panel, alone on black. `ANT 00` over `BEE 00`, in huge mono numerals, the red pulse dot live at the top.
Line: **TWENTY ROUNDS. TWO DRIVERS. NOTHING SCORED YET.**
The zeros are the hook — a championship caught at the instant before it starts.

## Key moments (the middle)
- **Round 01 card** — "ADELAIDE" in 7xl black italic, "Porsche 911 • The Season Opener", and the 20 / 10 / 30 session split counting up in mono, the Race number landing in red.
- **The calendar** — race rows stream in: Adelaide, Bathurst Historic, Monaco (Azure), Interlagos… with their format tags (F1 red, GT3 cyan, ENDUR yellow, SPRNT purple) snapping in beside them. The list is long on purpose: 20 rounds.
- **Track intel drawer** — the actual interaction. A row is clicked, the chevron rotates, the drawer slides open on **Spa Historic 1970 — 14.12km / 20 turns / Historical / "Twice as long as modern Spa."**
- **Points grid** — P1 25 down to P10 1, the P1 tile glowing red, then the footnote: **Fastest Lap: +1 Point.**

## Outro / punchline
Hard cut to black. The AMS2 mark, then:
**ANT vs BEE**
*Season 1.0 · Pre-season build*
Final line, mono, small, dry: **LIGHTS OUT SOON.**

## User flow worth showing
Real and specific — this is a working app, not a landing page:
1. **Entry** — the season calendar table, 20 rounds listed with class and format.
2. **Key action** — click a race row (the site's own instruction: "Click race for track intel"). Row goes active with a red left border, chevron rotates 180°.
3. **Result** — the intel drawer expands: Length, Turns, Type, Notes.
The centerpiece scenes (3) show exactly this.

## Tone
- Preset: `cinematic`
- Creative direction: F1 broadcast season-launch title sequence
- Interpretation: Big italic caps, full-bleed panels, dramatic reveals over quick cuts. Each line lands before the next begins. The restraint is the joke — nothing winks at the camera, because the site doesn't either.

## Format: landscape — 1920x1080
## Duration: 20s

## Visual identity (from the project)
- Background: `#050505` (`--bg-deep`)
- Surface: `#0f0f0f` (`--surface`), borders `#1f1f1f` (`--border`)
- Accent: `#ff3e3e` (`--brand-red`); UI also uses red-600 `#dc2626`
- Text: `#f0f0f0`, muted `#737373` (neutral-500)
- Format tag colors: F1 `#ef4444` · GT3 `#22d3ee` · ENDUR `#eab308` · SPRNT `#a855f7`
- Display font: Inter 900, italic, uppercase, tight tracking
- Body/number font: JetBrains Mono 700
- Strongest visual element: the rivalry panel's two huge mono zeros, and the red-bordered Round 01 hero card

## Share copy (draft)
Two drivers. Twenty rounds. One points table. I built a full F1-style race control dashboard so my mate and I can settle it properly.

## Audio direction
- Role: cinematic support — a driving bed that builds, not a corporate loop that just plays
- Music: `happy-beats-business-moves-vol-1-by-ende-dot-app.mp3` (120.19 BPM) — the most energetic bundled track; its strong-cue cluster at 16–24s is used deliberately for the outro slam
- Music treatment: start at 0:00, bed held under the hook, lift into the calendar sequence, full presence from 17s so the logo lands on peak energy; hard-ish fade in the final 0.4s
- Music cue guidance: preset cue file read (`cues/…vol-1….music-cues.md`). Target strong cues at **17.02s** (outro slam), **18.52s** (tagline), **20.02s** (final cut). Beat grid is 0.5s from 3.02s — sequential reveals ride *every other* beat (1.0s apart) so text stays readable, never every beat.
- Audio-reactive treatment: subtle — the red accent glow and the hero card presence may breathe with music energy. No waveform bars, no visualizers.
- SFX posture: sparse, motion-matched, broadcast-dry. UI-family sounds only (click/switch), one low impact for the outro.
- Audio-coupled moments: the 00/00 zeros settling; each calendar row arriving; the click on the race row and the drawer opening; the points tiles; the outro slam.
- Restraint rule: no engine noise, no crowd, no whooshes on every cut. This is a telemetry screen, not a trailer for a racing game. If a sound isn't matching a real on-screen movement, it doesn't go in.

## Storyboard

### Scene 1 — Rivalry / the zeros — 3.5s
Black. The rivalry panel fades up centered: `ANT` `00` over a hairline rule over `BEE` `00`, BEE and its number in red. Red pulse dot and "SEASON 1.0" micro-label above. Hook line settles beneath in mono caps: TWENTY ROUNDS. TWO DRIVERS. NOTHING SCORED YET. (Hold ≥1.3s settled — this is the hook, it gets the most reading time.)
Sequential/interaction: yes — ANT row settles, then BEE row 0.5s later, then the hook line.
Audio intent: quiet, held breath. Bed only, low.
Audio-coupled idea: a soft dry tick as each zero settles.
Music: low bed, restrained.
Transition mood: dramatic → Scene 2

### Scene 2 — Round 01: Adelaide — 4s
The hero card, red left border, fills frame. "NEXT EVENT: ROUND 01" micro-label with the live red dot. "ADELAIDE" slams in, 7xl black italic. Beneath: "Porsche 911 • The Season Opener". The three session stats reveal left to right — PRACTICE 20M / QUALIFYING 10M / RACE 30M — numbers counting up in mono, RACE in red.
Sequential/interaction: yes — three stat columns arrive one by one, ~1.0s apart (every other beat), numbers ticking up.
Audio intent: the season gets a date. Bed lifts.
Audio-coupled idea: a dry UI tick per stat column as its number lands.
Music: bed lifts, first real presence.
Transition mood: clean → Scene 3

### Scene 3 — The calendar, 20 rounds — 4.5s
The season calendar table. Header row, then race rows stream in from the top: R01 Adelaide / R02 Bathurst Historic / R03 Monaco (Azure) / R04 Cascavel / R05 Interlagos…, each with circuit name in italic caps and its format tag snapping in (F1 red, GT3 cyan, ENDUR yellow, SPRNT purple). The list keeps going past frame — the length is the point. Micro-label holds: "CLICK RACE FOR TRACK INTEL".
Sequential/interaction: yes — rows arrive one by one on every other beat, accelerating slightly, the last few blurring past to sell 20 rounds.
Audio intent: momentum. The season has scale.
Audio-coupled idea: a soft switch/click per row arrival, dropping in volume as they accelerate so it never rattles.
Music: full drive.
Transition mood: clean → Scene 4

### Scene 4 — Track intel (the interaction) — 4.5s
A cursor moves to the Spa Historic 1970 row and clicks. The row goes active — red left border, background lifts — the chevron rotates 180°, and the intel drawer slides open beneath it: **LENGTH 14.12km · TURNS 20 · TYPE HISTORICAL · NOTES "Twice as long as modern Spa."** The four fields land left to right. Hold the open drawer ≥1.2s so all four read.
Sequential/interaction: yes — simulated cursor click, then drawer expand, then four intel fields one by one.
Audio intent: the satisfying part. A real product doing a real thing.
Audio-coupled idea: one crisp click on the cursor press, a soft mechanical slide under the drawer opening, dry ticks on the field arrivals.
Music: full drive, holds.
Transition mood: hard → Scene 5

### Scene 5 — Points + outro slam — 3.5s
Fast: the points grid flashes up — P1 **25** glowing red, P2 18, P3 15, P4 12, P5 10 — and the footnote "FASTEST LAP: +1 POINT" ticks in beneath (hold ≥0.8s). Hard cut to black on the strong cue at 17.02s. The red AMS2 mark, then **ANT vs BEE** in huge italic caps, "SEASON 1.0 · PRE-SEASON BUILD" small beneath it, and last: **LIGHTS OUT SOON.**
Sequential/interaction: yes — the five points tiles snap in fast as a set, then the outro lockup.
Audio intent: arrival. Peak energy on the logo, then cut.
Audio-coupled idea: one low impact on the AMS2 slam; nothing under the final line but the bed.
Music: peak — align the slam to the 17.02s strong cue, tagline near 18.52s, final cut at 20.02s.
Transition mood: hard cut → end

**Total: 3.5 + 4 + 4.5 + 4.5 + 3.5 = 20.0s**

**Music mood for this video:** cinematic — driving bed that builds to a peak at the outro
**Audio summary:** A held-breath opening on the 00–00 scoreline, a steady build through the season card and the 20-round calendar, the most tactile moment on the real click-to-intel interaction, then peak energy landing exactly on the AMS2 slam before a hard cut to silence.
