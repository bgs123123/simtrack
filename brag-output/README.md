# brag-output

Produced by the `/brag` skill from this repo's `index.html`.

| File | What it is |
|---|---|
| `brag.mp4` | The launch video — 20s, 1920x1080, 30fps, music + SFX. The poster is baked in as frame 0. |
| `brag.jpg` | Poster frame (19.2s, the outro lockup). Use as `<video poster>` or a custom thumbnail upload. |
| `brag-plan.md` | Creative plan: 9-question rubric, tone, storyboard, audio direction. |
| `composition-brief.md` | The handoff brief to Hyperframes. |
| `share-copy.txt` | The share caption. |
| `composition/` | The Hyperframes project that renders `brag.mp4`. |

## Re-rendering

Three inputs are gitignored because they're restorable (see `.gitignore`):

```bash
cd composition

# 1. GSAP (vendored locally — the jsDelivr CDN is blocked in the build environment)
npm install && cp node_modules/gsap/dist/gsap.min.js assets/vendor/gsap.min.js

# 2. The music bed (already in this repo once, under the skill)
cp ../../.claude/skills/brag/assets/music/happy-beats-business-moves-vol-1-by-ende-dot-app.mp3 \
   assets/music/

# 3. Render
npx hyperframes check     # gate: must report 0 errors
npx hyperframes render --output ../brag.mp4 --quality delivery
```

Requires Node 22+, FFmpeg on PATH, and `npx hyperframes browser ensure` for the headless Chrome.

## Note on the UI

The live site (bgs123123.github.io/simtrack/) and the page's Tailwind/Lucide CDNs are unreachable from
the build environment, so the composition **recreates** the UI in hand-written CSS from `index.html`
rather than screen-capturing it. Every color, font, string and layout is taken from the source. Muted
greys are a few shades lighter than the site's `neutral-500/600` so the text clears WCAG AA at video
scale — without that, Hyperframes' contrast gate fails on 21 elements.
