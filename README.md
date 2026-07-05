# Innocent's Loan Tracker

A mobile-friendly, installable loan-tracking app. Logs approved/rejected applications, disbursements, targets, and daily reflections — all stored locally on the device (no backend, no account needed).

## Files

- `index.html` — the app itself
- `manifest.json` — makes the app installable to a phone home screen
- `sw.js` — service worker, lets the app open even with no signal
- `icon.png` — home-screen / browser-tab icon

All four files must sit in the **same folder** for install and offline mode to work.

## Put it on GitHub Pages

1. Create a new GitHub repository (public, since Pages needs public for free accounts).
2. Upload all four files to the root of the repo.
3. Go to **Settings → Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch".
5. Pick the `main` branch and `/ (root)` folder, then **Save**.
6. GitHub gives you a link like `https://yourusername.github.io/repo-name/` — wait a minute or two after saving for it to go live.

## Install it on a phone

- **iPhone (Safari):** open the link → tap the Share icon → **Add to Home Screen**.
- **Android (Chrome):** open the link → tap the menu (⋮) → **Add to Home screen** / **Install app**.

Once installed it opens full-screen like a normal app, and still works with no internet after the first load.

## Updating later

Whenever you upload a new version of `index.html` (or the other files), open **`sw.js`** and bump the version number in this line:

```js
const CACHE_NAME = 'loan-tracker-v1';
```

Change it to `v2`, `v3`, etc. This tells phones that already installed the app to fetch the new version instead of showing the old cached one.

## Data & privacy

Everything (applications, disbursements, journal entries, targets, reminders) is stored in the browser's local storage on the device itself. Nothing is sent anywhere. This also means data does **not** sync between devices — it stays wherever it was entered. If the browser's data is cleared, or the app is used on a different phone/browser, the history won't carry over.
