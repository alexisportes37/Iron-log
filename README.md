# AGOGI — The Art of Strength

Created by **Lexus Portes**.

This is a new, standalone, mobile-first Progressive Web App, not a reskin of IRON LOG. It includes a premium dashboard, a seven-day training plan, editable sets/reps/weights, completed set logging, exercise swapping, workout history, bodyweight tracking, JSON export/import, offline service worker, and an interactive **2D** muscle atlas.

## Publish using GitHub Pages

Upload the **contents** of this folder to the root of your existing `iron-log` repository, replacing the files of the same name. Keep the `icons` folder structure. In Settings → Pages, deploy from `main` branch and `/ (root)` folder. The website URL stays `https://alexisportes37.github.io/iron-log/`.

The app uses a fresh `agogi_fresh_v1` localStorage key. Previous IRON LOG data is not imported automatically. This build does **not** include a realistic 3D anatomical model. The muscle atlas is a selectable 2D educational diagram.

## Files

- `index.html`, `style.css`, `app.js`
- `manifest.webmanifest`, `sw.js`
- `icons/icon-192.png`, `icons/icon-512.png`

## Offline and testing

Serve over HTTPS for installability. On iPhone use Safari → Share → Add to Home Screen. After replacing a prior app, refresh in Safari and allow the service worker to update. Tested with JavaScript syntax checks and asset inspection; physical iPhone testing still needed.
