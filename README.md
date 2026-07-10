# Amazon Music · Adaptive UI

**Live: https://derbc-adaptive-ui.vercel.app**

A working Amazon Music client that adapts to the listener. Built by **DERBC Studio** for the CMU MHCI 2026 capstone with Amazon Music.

- **`/`** is the client in an iPhone frame, with a short reviewer guide beside it. On a phone the frame drops away.
- **`/adaptive-artist-v3.html`** is the artist profile on its own, with a console for scrubbing listener states (`?state=cold|casual|regular|superfan`, add `&lens=1` for the annotation overlay).

## Hosting note

The web export ships its icon fonts under `assets/node_modules/`, and Vercel refuses to serve any `node_modules` directory. This repo renames that folder to `assets/vendor/` and patches the bundle references after each export. If you regenerate the export, repeat this step or every vector icon renders as an empty box:

```bash
mv app/assets/node_modules app/assets/vendor
sed -i '' 's|assets/node_modules/|assets/vendor/|g' app/_expo/static/js/web/entry-*.js
```

Source: the [team repository](https://github.com/RabiatS/Amazon-Music-Adaptive-UI---DERBC). See `NOTICE` for attribution.
