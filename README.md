# uzairalimurtaza.github.io

Personal developer site for Uzair Ali Murtaza — independent Android developer, Lahore, Pakistan.

Hosts:
- Landing page (bio, app cards, contact)
- [Sound Meter privacy policy](https://uzairalimurtaza.github.io/soundmeter-privacy/)
- [`app-ads.txt`](https://uzairalimurtaza.github.io/app-ads.txt) (AdMob publisher verification — required since Jan 2025)

Plain HTML + CSS. No frameworks, no build step, no analytics, no trackers, no cookies.

---

## Deploy (one-time setup)

### Step A — Create the repo on GitHub (web UI)

1. Go to https://github.com/new
2. Repository name: **`uzairalimurtaza.github.io`** (must match exactly — this makes it a *user site* served at the domain root)
3. Visibility: **Public**
4. Do NOT add a README, .gitignore, or license (this folder brings its own)

### Step B — Push from this folder

```bash
cd "/Users/uzairalimurtaza/Life/Google-PlayStore/Google Play Store Apps/site/uzairalimurtaza.github.io"
git init -b main
git add .
git commit -m "Initial site"
git remote add origin https://github.com/uzairalimurtaza/uzairalimurtaza.github.io.git
git push -u origin main
```

(If git says the repo is already initialized / origin already exists, that's fine — it was pre-configured locally. Just run `git push -u origin main`.)

### Step C — Enable Pages

1. Repo → **Settings** → **Pages**
2. Source: **Deploy from a branch**
3. Branch: **main** / **(root)**
4. Save. Wait 30–60 seconds.

### Step D — Verify (each URL in an INCOGNITO window)

| URL | Expect |
|---|---|
| https://uzairalimurtaza.github.io/ | 200 — landing page |
| https://uzairalimurtaza.github.io/soundmeter-privacy/ | 200 — privacy policy |
| https://uzairalimurtaza.github.io/app-ads.txt | 200 — `text/plain`, single line: `google.com, pub-4816275844541583, DIRECT, f08c47fec0942fa0` |

## Troubleshooting

- **404 for a few minutes after the first push** — normal; GitHub Pages build queue. Refresh after 2–3 minutes.
- **app-ads.txt shows HTML instead of plain text** — the file is not at the repo root. It must sit next to `index.html`, not inside a folder.
- **Old content after an update** — GitHub Pages CDN caches for ~10 minutes; hard-refresh (Cmd+Shift+R) or wait.

## Maintenance notes

- **Privacy policy source of truth** is `apps/04-sound-meter/PRIVACY_POLICY.html` in the apps workspace. The copy at `soundmeter-privacy/index.html` is derived — resync it whenever the policy changes (comment at the top of that file says the same).
- **When Sound Meter goes live on Play**, replace the "Coming soon to Google Play" badge in `index.html` with a real Play Store link.
- **Custom domain (later, optional):** add a `CNAME` file at the repo root containing just the domain (e.g. `uzair.dev`), then configure DNS per GitHub Pages docs. Not needed for AdMob verification — the github.io URL works.
- **AdMob context:** this site + `app-ads.txt` + a live Play listing are the Week-1/Week-5 evidence items in `apps/04-sound-meter/ADMOB_REJECTION_RECOVERY_2026-06-10.md`. The Play Console listing's "Website" field must point to `https://uzairalimurtaza.github.io`.
