# Italy '26 — holiday app

A small Progressive Web App (same kind as Hub Pocket): **itinerary** + **expenses log**,
works offline, installs to your Home Screen with its own icon. Expenses save on the
device instantly; optional Gist sync keeps phone + iPad + Mac in step.

## Files
```
index.html              the whole app
manifest.webmanifest    name / icon / standalone window
sw.js                   service worker (launches offline)
icon-192 / 512 / maskable-512.png
```

## Get it on your phone (one-time, ~10 min)

This needs hosting at a real web address — opening the file from the Files app
won't reliably keep your data. Use GitHub Pages, exactly like Hub Pocket.

1. **You:** create a new public GitHub repo, e.g. `italy-2026`.
2. **You:** upload the **contents of this `app/` folder** to the repo root
   (so `index.html` sits at the top, not inside an `app/` subfolder).
3. **You:** Settings → Pages → deploy from `main`. Wait for the green URL,
   e.g. `https://<you>.github.io/italy-2026/`.
4. **On the iPhone:** open that URL in Safari → Share → **Add to Home Screen**.
   It now opens full-screen with the sun icon. Do the same on the iPad.

## Turn on sync across devices (optional but recommended)

Without this, each device keeps its own list. With it, they merge.

1. **You:** create a Gist on github.com (can be secret) with one file named
   `holiday-italy-2026.json`, content `{}`.
2. **You:** make a token with **only** the `gist` scope.
   (Tip: a separate GitHub account keeps it away from your other gists — same
   reasoning as the work Hub.)
3. In the app: tap **⚙ → paste the Gist ID + token → Save**. The dot by the title
   shows `·synced`. Repeat on the iPad/Mac with the *same* Gist ID + token.

Sync is read-merge-write by entry, last edit wins, deletions propagate — so it's
safe to add on the phone and the iPad and they won't clobber each other.

## Using it
- **Itinerary tab** — flights, both stays, day-by-day, the must-not-miss bits.
  Quick reference; the full detail/maps are in the printed booklet.
- **Expenses tab** — type the amount, pick €/£, optionally category + who paid,
  tap **Add**. Running £/€ total at the top; set a budget in ⚙ to see what's left.
  The exchange rate is editable in ⚙ (default £1 = €1.15).
- **⚙ Settings** — rate, budget, sync, **Export backup** (a JSON file you can keep
  or import elsewhere), and clear.

## What I can't do for you
Creating the GitHub repo/Gist, generating the token, and pasting credentials are
yours — I prepare the files and the steps, you hold the keys. (Same split as the Hub.)

## Editing later
The app is one self-contained `index.html` — no build step. Per your home-iMac code
rule, do any edits there. Itinerary content is the `DAYS` array and the itinerary
cards near the top of the file.
