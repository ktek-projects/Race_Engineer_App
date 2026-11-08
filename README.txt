SETUP SHEET PRO - PWA PACKAGE
=============================

Folder layout (keep exactly like this)
  index.html              the app (self-contained, runs offline)
  manifest.webmanifest    install info (name, icons, colours, screenshots)
  sw.js                   service worker (offline caching)
  icons/                  icon-192.png, icon-512.png, icon-maskable-512.png, apple-touch-icon.png
  screenshots/            wide.png, narrow.png (shown in the install dialog)

The app file MUST be called index.html and sit beside manifest.webmanifest and sw.js.

IMPORTANT: a PWA can only be installed when served over https:// (or http://localhost).
Opening index.html straight from disk still works as a normal web page, but it won't be installable.

Hosting (free, drag-and-drop the whole folder)
  - Netlify Drop:  https://app.netlify.com/drop
  - Cloudflare Pages, GitHub Pages, or any web server

Install
  - Android / Chrome:  open the hosted address > menu > "Install app" / "Add to Home screen"
  - iPhone / Safari:   open the hosted address > Share > "Add to Home Screen"
  - Desktop Chrome/Edge: install icon in the address bar

UPDATING AN EXISTING INSTALL (step by step)
  1. Back up first: in the app press Backup > Export backup file on each device that has data.
  2. Replace index.html with the new version (keep the file name index.html).
  3. In sw.js change CACHE_VERSION to a new value, e.g. 'setup-sheet-pro-v4'. Use a new value every time
     any file changes. If sw.js does not change, installed copies may keep serving old files.
  4. If the app name changed, edit "name" and "short_name" in manifest.webmanifest. Leave "id",
     "start_url" and "scope" alone: they identify the installed app.
  5. If the icons or screenshots changed, replace the files in icons/ and screenshots/ using the same file names.
  6. Upload the whole folder to the SAME hosting address as before (same address = same saved data).
  7. On each device: open the app while online, close it completely, then open it again. A second
     close-and-open may be needed before the new version shows.
  8. Android/Chrome updates the installed app's name and icon by itself within a day or so.
     iPhone/Safari does not: to pick up a new name or icon, delete the home-screen app and add it again
     (export a backup first, then import it afterwards).

Your data
  Setups and track maps are stored in the browser on that address. A different address (or the file opened
  from disk) is a separate store, so use Backup > Export backup file before moving to a new address.
