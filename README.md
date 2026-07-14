# atharva-site

Personal portfolio — a single self-contained `index.html`, no build step,
no framework. Pure HTML/CSS/JS with one CDN import (Lenis, for smooth
scroll). Everything else — the intro loader, the cursor-driven liquid
image reveal in the hero, the spring-feel entrance animations, the
scroll-triggered stat count-up — is hand-rolled vanilla JS.

Live at [atharvakalange.com](https://atharvakalange.com).

## Running it locally

No build step. Just serve the directory:

```bash
python3 -m http.server 4173
```

Then open `http://localhost:4173`.

## Deployment

GitHub Pages, deployed from `main` (root). Custom domain and DNS run
through Cloudflare, which also serves the Web Analytics beacon.

**Repo must stay public** — GitHub Pages on the free tier only builds
from public repos. Flipping this private silently disables Pages until
it's flipped back and the source is re-selected under Settings → Pages.

The contact form posts to Formspree (`FORMSPREE_ENDPOINT` near the
bottom of the `<script type="module">` block).

## Structure

Everything lives in `index.html`: one `<style>` block, one body, one
`<script type="module">`. The two hero images (a network-graph visual and
a circuit-board visual, swapped by the cursor) are generated as inline
SVG data URIs at runtime — no external image hosting, no hotlinked
assets.
