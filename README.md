# atharva-site

Personal portfolio — a single self-contained `index.html`, no build step,
no framework. Pure HTML/CSS/JS with one CDN import (Lenis, for smooth
scroll). Everything else — the intro loader, the cursor-driven liquid
image reveal in the hero, the spring-feel entrance animations, the
scroll-triggered stat count-up — is hand-rolled vanilla JS.

## Running it locally

No build step. Just serve the directory:

```bash
python3 -m http.server 4173
```

Then open `http://localhost:4173`.

## Before this goes fully live

1. **Wire up the contact form.** `FORMSPREE_ENDPOINT` near the bottom of
   the `<script type="module">` block is currently a placeholder
   (`https://formspree.io/f/YOUR_FORM_ID`). To make it real:
   - Go to [formspree.io](https://formspree.io), sign up free, create a
     new form.
   - Copy the endpoint it gives you (`https://formspree.io/f/xxxxxxxx`).
   - Replace `FORMSPREE_ENDPOINT` in `index.html` with that URL.
   - Submissions will then land in your Formspree inbox / forward to your
     email, no backend needed.
2. **Fill in the real stats.** The `STATS` array (same script block) has
   one real number (`5` open-source systems shipped) and three
   placeholders marked `value: null, display: 'XX'`. Swap each `null` for
   a real number once you know it, and delete the `— edit me` suffix from
   the label.
3. **Double check the social links** (GitHub is correct; LinkedIn and X
   are placeholder URLs — update them to your actual profiles).

## Structure

Everything lives in `index.html`: one `<style>` block, one body, one
`<script type="module">`. The two hero images (a network-graph visual and
a circuit-board visual, swapped by the cursor) are generated as inline
SVG data URIs at runtime — no external image hosting, no hotlinked
assets.
