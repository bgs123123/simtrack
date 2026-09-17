---
workflow: product-launch-video
flow: automation
storyboard: yes
message: "Two mates gave their grudge match the full Formula 1 treatment — 20 real circuits, real session formats, a real points table, and nothing scored yet"
destination: discord
aspect: 1920x1080
language: en
length: 45s
angle: site-tour
voice: am_michael
style_preset: code-editorial
---

## Intent

A 45-second showcase of the AMS2 Ant vs Bee Championship — a race-control dashboard
for a 20-round Automobilista 2 season between exactly two drivers, Ant and Bee.

**This is a personal project, not a product.** Nobody is signing up for anything and
nothing is being sold. No marketing language, no "streamline your season", no feature
benefits. The register is deadpan F1 broadcast: state the facts seriously and let the
absurdity of a two-person world championship do the work. The site itself never winks
at the camera, so neither does the video.

The scoreline is 00–00 — the season hasn't started. That's the frame for the whole piece.

## Assets

- /home/user/simtrack/index.html — the site itself; the single source of all copy, colors and data (the `raceData` array holds all 20 circuits with their intel).
- /home/user/simtrack/.claude/skills/brag/assets/music/happy-beats-business-moves-vol-1-by-ende-dot-app.mp3 — the music bed. The user chose this specific file; do not substitute a library track. 2:44 long, 120.19 BPM.

## Customizations

- **Narration is on.** Local Kokoro TTS (not signed in to HeyGen). Deadpan delivery — a race director reading a briefing, not an announcer selling a product. Music ducks under the voice.
- **The circuits are the centrepiece.** The user explicitly chose "more circuits + track intel" as the material for the extra 25 seconds over the standings tracker, the session formats, or a heavier rivalry angle. Feature multiple track intel drawers with their real notes, e.g.:
  - Monaco (Azure) — 3.33km / 19 turns / "Tightest circuit in the world. Passing is nearly impossible."
  - Spa Historic 1970 — 14.12km / 20 turns / "Twice as long as modern Spa."
  - Le Mans 24 — 13.63km / 38 turns / "Home of the famous 24-hour race."
  - Laguna Seca — 3.60km / 11 turns / "Features the 'Corkscrew' - a 5-story drop."
  - Monza — 5.79km / 11 turns / "The Temple of Speed."
  - Bathurst Historic — 6.21km / 23 turns / "The mountain straight and winding descent are legendary."
- Keep the 00–00 rivalry scoreline as the opening hook and the closing note.

## Notes

- Copy must come from the site verbatim wherever possible. The previous 20s cut invented two
  lines ("Twenty rounds. Two drivers. Nothing scored yet." and "Lights out soon.") — they landed
  well and may be reused, but new invented copy should be flagged rather than slipped in.
- Palette from the site: bg `#050505`, surface `#0f0f0f`, border `#1f1f1f`, brand red `#ff3e3e`,
  text `#f0f0f0`. Format tag colors: F1 `#ef4444`, GT3 `#22d3ee`, ENDUR `#eab308`, SPRNT `#a855f7`.
  Fonts: Inter (900 italic, uppercase, tight tracking) for display, JetBrains Mono for numbers.
- The site's muted greys (`neutral-500/600`) fail WCAG AA at video scale; lift them a few shades
  as the previous cut did, or `hyperframes check` fails the contrast pass.
- Environment: the live URL (bgs123123.github.io/simtrack/) and the page's Tailwind + Lucide CDNs
  are blocked by the egress proxy. The capture is taken from a locally served copy with those
  dependencies vendored from npm, so the screenshots are of the real page as designed.
