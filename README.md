# Drop Zone Print — static site

Single-page promotional site plus two legal pages. Plain HTML + one stylesheet, no build
step, no framework, no dependencies. Total page weight is a few hundred KB and it works
with JavaScript disabled (the drop-list form is the only script; without it the field
simply does nothing).

```
site/
├── index.html          Home — hero, 4 collections, custom drop, story, facts, drop list, follow
├── terms.html          Terms of Service
├── privacy.html        Privacy Policy
├── css/style.css       All styling (design tokens at the top of the file)
├── assets/
│   ├── dzp-lockup.png          OD green lockup — light surfaces
│   ├── dzp-lockup-cream.png    Cream lockup — dark surfaces (footer)
│   ├── dzp-mark.png            Parachute mark only
│   ├── favicon.png             512×512
│   ├── apple-touch-icon.png    180×180
│   └── og-image.png            1200×630 social share card
├── robots.txt
├── sitemap.xml
└── .nojekyll           Tells GitHub Pages to serve files as-is
```

## Publish to GitHub Pages

```bash
git clone https://github.com/tiguere561/dropzone.git
cd dropzone
# copy the CONTENTS of this site/ folder into the repo root
git add -A && git commit -m "Drop Zone Print site" && git push
```

Then: **Settings → Pages → Source: Deploy from a branch → `main` / `/ (root)` → Save.**
Live in about a minute at `https://tiguere561.github.io/dropzone/`.

For a custom domain, add a file named `CNAME` at the repo root containing just
`dropzoneprint.com`, then point the domain's DNS at GitHub Pages.

## Brand tokens

Defined once in `css/style.css`:

| Token | Value | Use |
| --- | --- | --- |
| `--od` | `#4B5320` | OD green — accent, buttons, layer lines |
| `--od-d` | `#3C421A` | OD green hover |
| `--cream` | `#F5F1E8` | Page ground |
| `--cream-2` | `#EDE8DA` | Cards, alternating band |
| `--cream-3` | `#E5DECB` | Card hover |
| `--ink` | `#14150F` | Near-black — text, dark bands, footer |
| `--notch` | `18px` | Cut-corner size on cards and panels |

Type: **Archivo** 900 at 88% width (display, matches the logo wordmark) · **Barlow** (body) ·
**JetBrains Mono** (labels and technical strips). All from Google Fonts.

The canopy layer-line motif is `.layers` (7 stacked rules, narrow to wide) as a section
divider, and `.stack` (4 rules) as the small mark on each collection card.

## Before you go live — edit these

1. **`Printed in Florida, USA`** — `index.html` (proof strip). Set your real city/state.
2. **Etsy collection links** — all four cards and every "Shop" button point at
   `https://www.etsy.com/shop/dropzoneprint`. Swap in real Etsy section URLs when the
   shop sections exist.
3. **Collection names, materials and copy** — Desk Duty / Field Kit / Display Line /
   Custom Drop are drafts. Same for `3–5 day` shipping, `24 hour` quotes, `500+ orders`.
4. **Story section** — written from the brief, not from your actual history. Rewrite it.
5. **Legal** — `terms.html` names Palm Beach County, FL as venue, a 14-day damage window,
   and `privacy.html` says custom files are kept two years. Confirm all three, and have
   counsel read both pages before publishing.
6. **Canonical / sitemap URLs** assume `tiguere561.github.io/dropzone/`. Update if you
   use a custom domain.

## Drop list

The form has no backend. On submit it opens the visitor's mail client with a pre-filled
message to `support@dropzoneprint.com`. When you're ready for real list management, drop
in a Mailchimp/Buttondown/Kit form action and delete the inline `<script>` at the bottom
of `index.html` — then update `privacy.html` section 03, which currently promises no
third-party processing.

---

© 2026 Drop Zone Print. A Pico Duarte Holdings LLC company.
