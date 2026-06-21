# TalkVisual305 Thumbnail Generator

Local, browser-based tool for generating on-brand 1280x720 YouTube thumbnails and
1080x1920 YouTube Shorts covers for the TalkVisual305 channel. No AI image generation,
no build step — a single HTML file styled with CSS, exported to PNG with html2canvas.

## Run it

Open [`index.html`](index.html) directly in Chrome — either double-click the file or,
once this repo is published to GitHub Pages, just visit the Pages URL.

## What it does

- Two formats: 16:9 YouTube thumbnail and 9:16 Shorts cover (centered stacked caption style)
- Two layouts: Panel wide (3-person table shot) and Guest focus (single photo + navy panel)
- Mozi-style headline: small lead-in + big alternating yellow/green emphasis words,
  white fill, black stroke, drop shadow
- Navy (`#0A1F33`) scrim over every photo so raw frame grabs look graded, not raw
- Logo badge corner + optional "NEW EPISODE" accent badge
- Exports a pixel-accurate PNG named from the headline or a filename you set

## Assets

- `assets/logo/placeholder-logo.svg` — swap with the real TalkVisual305 logo, same filename/path
- `assets/samples/sample-panel.svg` — placeholder panel shot for testing; replace via the file
  picker in the tool with real frame grabs

## Adding new layouts

Layout variants are CSS classes on `#thumb-canvas` (`layout-panel-wide`, `layout-guest-focus`)
combined with an orientation class (`orientation-vertical` for 9:16). Add a new `<option>` to
`#layoutSelect`, a matching CSS block, and a branch in `applyLayout()` in the inline `<script>`.

## Publishing to GitHub Pages

1. Create a new repo on github.com (public is fine — no sensitive data here).
2. In GitHub Desktop: **File → Add Local Repository**, point it at this folder, then
   **Publish repository**.
3. On github.com, go to the repo's **Settings → Pages**, set **Source** to
   "Deploy from a branch", branch `main`, folder `/ (root)`, Save.
4. After a minute, the tool is live at `https://<your-username>.github.io/<repo-name>/`.

Share that URL with Demmetrius — same tool, same browser, no install.
