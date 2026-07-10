# Amazon Music · Adaptive UI — DERBC Studio

**Live: https://derbc-adaptive-ui.vercel.app**

Prototype for the CMU MHCI 2026 capstone with Amazon Music.

- **`/`** — the full client in an iPhone frame (best on a laptop; on a phone the frame drops away). Tap around: Home, Find, Library, Maestro, and the **Olivia Rodrigo artist page** (adaptive profile), with the in-player **Lyrics** and **X-Ray** sheets on Now Playing.
- **`/adaptive-artist-v3.html`** — the artist profile standalone, with the moderator console for scrubbing listener states (`?state=cold|casual|regular|superfan`, `&lens=1` for the annotation overlay).

## Hosting note

The web export ships its icon fonts under `app/assets/node_modules/…` — if you
mirror this build into a repo whose `.gitignore` excludes `node_modules/`, add
an exception for that path or every vector icon renders as a tofu box.

Source: [Amazon-Music-Adaptive-UI---DERBC](https://github.com/RabiatS/Amazon-Music-Adaptive-UI---DERBC). See `NOTICE` for attribution.
