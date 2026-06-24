# Bugaboos 2027 Tracker — deploy & install

A self-contained PWA. Everything is in this folder — no build step, no dependencies.

## Files
- index.html ............ the app (all CSS/JS inline)
- manifest.webmanifest .. PWA manifest
- sw.js ................. service worker (offline caching)
- icon-180.png ......... apple-touch-icon (iPhone home screen)
- icon-192/512.png ..... manifest icons

## Deploy to Cloudflare Pages (your usual flow)

1. Push this folder to a GitHub repo:
   git init
   git add .
   git commit -m "bugaboos tracker pwa"
   gh repo create bugaboos-tracker --public --push

2. Cloudflare dashboard -> Workers & Pages -> Create application -> Pages
   -> Connect to Git -> pick the repo
   - Framework preset: None
   - Build command: (blank)
   - Build output directory: (blank)
   -> Save and Deploy

3. You get a URL like bugaboos-tracker.pages.dev

## Install on the iPhone 13

1. Open the .pages.dev URL in SAFARI (must be Safari).
2. Tap Share -> Add to Home Screen -> Add.
3. Launch from the icon. It opens full-screen and works offline.
   Your checkmarks, lifts, and logs save on the phone.

## Updating later
Edit index.html, bump CACHE in sw.js (v1 -> v2), push to GitHub.
Pages redeploys in ~30s. Reopen the app twice to pick up the new version.

## Note on data
Data lives in this browser/app on the phone. It is not synced to a server.
Back it up by adding an export-to-JSON button before you accumulate months of logs.
