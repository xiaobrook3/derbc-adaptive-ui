# Amazon Music · Adaptive UI — DERBC Studio

**Live: https://derbc-adaptive-ui.vercel.app**

Prototype for the CMU MHCI 2026 capstone with Amazon Music.

- **`/`** — the full client in an iPhone frame (best on a laptop; on a phone the frame drops away). Tap around: Home, Find, Library, Maestro, and the **Olivia Rodrigo artist page** (adaptive profile), with the in-player **Lyrics** and **X-Ray** sheets on Now Playing.
- **`/adaptive-artist-v3.html`** — the artist profile standalone, with the moderator console for scrubbing listener states (`?state=cold|casual|regular|superfan`, `&lens=1` for the annotation overlay).

## Hosting note

The web export ships its icon fonts under `assets/node_modules/…`, and Vercel
refuses to upload or serve any `node_modules` directory — so this repo renames
that folder to `assets/vendor/` and patches the bundle references after each
export. If you regenerate the export, repeat that step or every vector icon
renders as a tofu box:

```bash
mv app/assets/node_modules app/assets/vendor
sed -i '' 's|assets/node_modules/|assets/vendor/|g' app/_expo/static/js/web/entry-*.js
```

Source: [Amazon-Music-Adaptive-UI---DERBC](https://github.com/RabiatS/Amazon-Music-Adaptive-UI---DERBC). See `NOTICE` for attribution.
