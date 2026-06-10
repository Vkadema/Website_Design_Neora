# Neora X1 — landing page

Single-file landing page (`index.html`) reproducing the two Figma sections with the
scroll-scrub video choreography.

## Host it (free)
Upload these files to the **same folder** on any static host (GitHub Pages, Netlify
drop, Cloudflare Pages, Vercel):

- `index.html`
- `neora-video.mp4`  ← web-optimized 1080p, every frame is a keyframe (smooth scrubbing)
- `poster.jpg`       ← first-frame placeholder

That's it — open `index.html`.

## Video source
`index.html` first tries the local `./neora-video.mp4`; if it isn't found it falls back
to the original on GitHub. To force one or the other, edit the `SOURCES` array near the
top of the `<script>`.

## Fonts
Loaded from Google Fonts: **Zalando Sans Expanded** (display) and **Zalando Sans** (body).
If your network blocks Google Fonts, self-host the woff2 files and swap the `<link>` for
an `@font-face` block.

## Tuning the motion
All timings live in the constants block at the top of the `<script>`:
- `FREEZE` (7.9 s) — where the intro stops
- `SCRUB_END_P` — scroll progress at which the video reaches its last frame
- `TITLE_IN`, `CARD_STARTS`, `CARD_WIN` — section-2 reveal windows
- `.track { height: 320vh }` in the CSS controls how much scrolling the scrub takes
