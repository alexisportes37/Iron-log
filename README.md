# IRON LOG — Installable iPhone workout tracker

IRON LOG is a static Progressive Web App (PWA) built with HTML, CSS, and JavaScript. It runs in Safari, works offline after the first online load, and stores workout data on the device using localStorage. No Mac, Xcode, backend, or subscription is needed to run the app.

## Features
- Monday Chest + Back, Tuesday Legs, Wednesday Shoulders + Arms, Thursday Recovery, Friday Legs + Abs. CBum-inspired example exercise selection, editable set counts.
- Weight/reps per set, completion checkboxes, autosaved in-progress drafts, workout notes.
- Dated persistent history, per-exercise highest completed-set weight records.
- Body-weight log, weekly workout/set/volume dashboard.
- JSON export/import backup, with validation and confirmation before replacement.
- Dark/green interface, custom icon, standalone home-screen display, offline service worker.

## Important: Hosting is required for iPhone installation
Opening `index.html` directly from the iPhone Files app does **not** provide a reliable installable PWA. The site must be hosted via HTTPS. One simple free option is GitHub Pages:

1. On your iPhone, create or sign in to a GitHub account at https://github.com.
2. Create a new **public** repository, for example `iron-log`.
3. Upload **all files and folders inside `iron-log-web`** to the repository root, preserving `icons/`.
4. Open repository **Settings → Pages**; under **Build and deployment**, select **Deploy from a branch**, branch **main**, folder **/(root)**; save.
5. Wait for deployment. Visit the HTTPS URL shown under Pages, commonly `https://YOUR-USERNAME.github.io/iron-log/`.
6. On your iPhone, open that URL in **Safari**, tap **Share → Add to Home Screen → Add** (on some iOS versions, select **Open as Web App** if offered).
7. Open IRON LOG from the new Home Screen icon while online once. It can then run offline with cached assets.

Alternatively, host the folder on any static HTTPS host (Netlify, Cloudflare Pages, etc.). A public code repository does **not** publish your workout data; that data stays in the browser on your phone.

## Backups and storage caveats
- Data stays on the device/browser profile; it is not automatically synchronized to iCloud or other devices.
- Deleting the web app, clearing Safari website data, private browsing, or iOS storage cleanup may remove local records. **Export JSON backups regularly** and save them to Files/iCloud Drive.
- Importing a backup **replaces** current workout records, body-weight records and drafts.
- Unit switching changes the label only; it does not convert existing numbers. Pick lb or kg before entering data.
- Personal records are the heaviest completed-set weight, not a calculated one-rep max.
- The workout split is an example, not personalized medical or exercise advice.

## Developer test
Serve locally (not `file://`): `python3 -m http.server 8000` from this folder, then visit `http://localhost:8000` in a browser. Service workers work on localhost or HTTPS. To update the cached app, increment the `CACHE` value in `sw.js` before redeploying.

## Files
`index.html` — app shell; `style.css` — responsive dark theme; `app.js` — workout logic and local storage; `sw.js` — offline caching; `manifest.webmanifest` — installation metadata; `icons/` — custom app icons.

## Future App Store release
This is a PWA, **not** a native iOS App Store binary. A future native or wrapped App Store submission requires Apple Developer enrollment, signing, an appropriate iOS build toolchain/service, store metadata, privacy disclosures, and review. Apple may reject an app that merely wraps a website without sufficient app-like functionality.

## Version 2 upgrade (muscle education + exercise swapping)

This upgrade keeps the original `iron-log-data-v1` localStorage key so your saved workouts remain accessible on the **same device and same website address**. Still export a backup from Settings before replacing files.

### New features
- Tap **Swap exercise** in any active exercise card. Choose a suggested alternative or type a custom exercise. Completed sets are preserved as a separate exercise entry; incomplete sets are discarded when swapping.
- **MUSCLES** tab: tap simplified muscle areas or labels, then switch Beginner/Advanced explanations. This is a stylized educational diagram, not a licensed detailed 3D anatomical model.

### Updating GitHub Pages on a phone
1. Export your existing workout backup first.
2. Replace `index.html`, `app.js`, `style.css`, and `sw.js` in the **root** of the same GitHub repository. Keep `manifest.webmanifest` and `icons/` as they were. Do **not** upload the ZIP itself as the site.
3. Wait for GitHub Pages to deploy, reload the app online, and reopen it from the Home Screen. The service worker cache is versioned `iron-log-v2`. If an old page remains, close the installed app and refresh in Safari/Chrome.
4. Confirm your previous History is still present. Avoid clearing website data or uninstalling until you have exported a backup.

## Creator credit
Created by **Lexus Portes**. The creator credit appears in the Settings screen.
