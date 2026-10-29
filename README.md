# Race_Engineer_App

RACE ENGINEER APP - PWA PACKAGE
================================

Files
  index.html            the app (self-contained, runs offline)
  manifest.webmanifest  install info (name, icons, colours)
  sw.js                 service worker (offline caching)
  icons/                app icons

IMPORTANT: a PWA can only be installed when served over https:// (or http://localhost).
Opening index.html straight from disk still works as a normal web page, but it won't be installable.

Easiest ways to host it (free, drag-and-drop the whole folder):
  - Netlify Drop:  https://app.netlify.com/drop
  - Cloudflare Pages, GitHub Pages, or any web server

Install
  - Android / Chrome:  open the hosted address > menu > "Install app" / "Add to Home screen"
  - iPhone / Safari:   open the hosted address > Share > "Add to Home Screen"
  - Desktop Chrome/Edge: install icon in the address bar

Updating later
  When you change index.html, edit CACHE_VERSION in sw.js (e.g. race-engineer-v2) so installed copies refresh.

Your data
  Setups and track maps are stored in the browser on that address. A different address (or the file opened
  from disk) is a separate store, so use Backup > Export backup file before moving to a new address.
