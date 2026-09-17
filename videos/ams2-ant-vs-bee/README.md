# ams2-ant-vs-bee — 45s launch video

Built with the `product-launch-video` HyperFrames workflow from this repo's `index.html`.

| Path | What it is |
|---|---|
| `renders/video.mp4` | The video — 46.3s, 1920x1080, narrated, poster baked as frame 0 |
| `renders/video-discord.mp4` | Same cut compressed to 3.3MB for Discord's upload limit |
| `renders/poster.jpg` | Poster frame (the outro lockup) |
| `BRIEF.md` | The confirmed intent — message, tone, what the extra 25s is for |
| `STORYBOARD.md` | 8 frames: narration, durations, shot sequences, `## Video direction` |
| `SCRIPT.md` | The locked narration, 8 lines |
| `frame.md` | Design system — the `code-editorial` preset remixed onto the site's dark palette |
| `capture/` | The real captured page: screenshots, DOM tokens, visible text |
| `compositions/frames/` | One HTML composition per frame |
| `assets/` | Screens, fonts, narration WAVs, vendored GSAP |

## How the capture was made

The live site (bgs123123.github.io/simtrack/) and the page's Tailwind + Lucide CDNs are blocked by
the build environment's egress proxy. So the page was served locally with those two dependencies
installed from npm and its CSS rebuilt against `index.html` — the real page, real styles, just
resolved locally. `capture/extracted/tokens.json` holds the tokens read off the live DOM.

The five `capture/screenshots/intel-*.png` plates were captured with each track's intel drawer
genuinely open, by driving the real page. They are not mockups. All plates are 2x
(3840x2160 behind a 1920x1080 CSS box) so the camera push-ins have real pixels.

## Re-rendering

Two inputs are gitignored because they're restorable:

```bash
# the music bed (already in this repo once, under the skill)
cp ../../.claude/skills/brag/assets/music/happy-beats-business-moves-vol-1-by-ende-dot-app.mp3 \
   assets/music/bed.mp3

npx hyperframes check      # gate: must report 0 errors
npx hyperframes render --skill=product-launch-video --quality high --output renders/video.mp4
```

Needs Node 22+, FFmpeg, and `npx hyperframes browser ensure`. Narration was generated locally with
Kokoro (`pip install kokoro-onnx soundfile`) — the WAVs in `assets/voice/` are committed, padded
with deliberate silence so the deadpan delivery has pauses.

## Notes

- Narration lines not taken verbatim from the site: "A championship that hasn't started yet",
  "Thirty to settle it", "Monza just has a nickname", "There are two cars", "Lights out soon."
  Everything else is the site's own copy or its own data.
- The music bed is lifted to 0.34 and ducks only to 0.17 under narration. An earlier mix ducked to
  0.11 and the track became inaudible, because the eight lines run nearly back to back.
