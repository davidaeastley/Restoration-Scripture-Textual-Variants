# Book of Moses — Textual Comparison (installable PWA)

This folder is a complete, self-contained web app: `index.html`, `manifest.json`,
`sw.js` (service worker), and two icon files. For Android's "Install app" prompt
and offline support to actually work, these files need to be served over HTTPS
from a real web host — browsers won't grant install/offline capability to files
opened directly from local storage (`file://`).

The good news: several hosts will do this for free, with no server setup.

## Easiest: GitHub Pages

1. Create a new repository on github.com (public or private both work).
2. Upload all 5 files in this folder to the repository (drag-and-drop on the
   "Add file → Upload files" screen works fine).
3. Go to the repo's **Settings → Pages**, set the source to the `main` branch
   (root), and save.
4. GitHub gives you a URL like `https://yourname.github.io/reponame/`.
   Open that on your Android phone in Chrome.
5. Chrome should show an "Install app" banner, or you can open the
   ⋮ menu → **Install app** / **Add to Home screen** manually.

## Alternatives (also free, no account needed for a quick test)

- **Netlify Drop** — go to https://app.netlify.com/drop and drag this whole
  folder onto the page. It gives you a live HTTPS URL immediately.
- **Cloudflare Pages** or **Vercel** — both support dragging a folder into
  their dashboard for a static deploy.

## After installing

Once installed, the app opens full-screen (no browser address bar), with the
icon on your home screen, and the service worker caches the app shell so it
keeps working without a network connection after the first load.

## Updating the data later

If verses get corrected or a fourth column gets added, the new `index.html`
just needs to be re-uploaded to the same host. The service worker's cache
name (`moses-compare-v1` in `sw.js`) would need to be bumped to `v2` etc. so
returning visitors pick up the new version instead of a stale cached copy.
