# Caddie — install guide

One-time setup, ~10 minutes. No server, no API key. Data lives on your phone.

## 1. Put it on GitHub Pages

1. Go to github.com → New repository. Name it `caddie`, set it Public, create.
2. On the repo page: **Add file → Upload files**. Drag in all four items:
   `index.html`, `sw.js`, `manifest.json`, and the `icons` folder.
   Commit.
3. Repo **Settings → Pages** → under "Branch" pick `main`, folder `/ (root)`, Save.
4. Wait ~1 minute. Your URL is `https://YOURUSERNAME.github.io/caddie/`

## 2. Install on your iPhone

1. Open that URL **in Safari** (not Chrome — Chrome on iOS can't install PWAs).
2. Let it load fully once (this caches it for offline).
3. Share button → **Add to Home Screen** → Add.
4. Open it from the home screen icon once while online.

Done. It now runs in airplane mode, opens full-screen with no Safari chrome,
and logged shots persist in IndexedDB. Because it's home-screen-installed,
iOS exempts it from the 7-day site-data eviction.

## 3. Updating the app later

1. Edit/replace files in the GitHub repo.
2. In `sw.js`, bump `VERSION` (e.g. `caddie-v1` → `caddie-v2`).
3. On the phone, open the app twice while online — first open fetches the
   new worker, second open loads through it.

## Data safety

- **Export** (Bag tab) downloads a JSON backup of every logged shot.
  Do this every few rounds and it lives in Files/iCloud.
- **Import** restores from a backup — including onto a new phone.
- Deleting the app from the home screen deletes its data. Export first.
