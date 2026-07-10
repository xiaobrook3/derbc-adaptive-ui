# Amazon Music · Adaptive UI

**Live: https://derbc-adaptive-ui.vercel.app**

A working Amazon Music client that adapts to the listener. Built by **DERBC Studio** for the CMU MHCI 2026 capstone with Amazon Music.

- **`/`** is the client itself. On desktop it renders as a phone-width column; on a phone it fills the screen. The adaptive artist profile is one tap from Home (the Olivia Rodrigo card).
- **`/phone.html`** wraps the client in an iPhone frame with a short reviewer guide beside it, for laptop grading.
- **`/adaptive-artist-v3.html`** is the artist profile on its own, with a console for scrubbing listener states (`?state=cold|casual|regular|superfan`, add `&lens=1` for the annotation overlay).

## Hosting notes

Two rules learned the hard way. First, the web export ships icon fonts under `assets/node_modules/`, and Vercel refuses to serve any `node_modules` directory, so rename it and patch the bundle after each export:

```bash
mv assets/node_modules assets/vendor
sed -i '' 's|assets/node_modules/|assets/vendor/|g' _expo/static/js/web/entry-*.js
```

Second, keep the SPA fallback rewrite scoped to paths without a dot (see `vercel.json`). A catch-all rewrite feeds HTML to stale hashed-asset requests as a 200, and any client holding a cached shell boots to a black screen forever.

Source: the [team repository](https://github.com/RabiatS/Amazon-Music-Adaptive-UI---DERBC). See `NOTICE` for attribution.
