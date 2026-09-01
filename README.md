# Hubhood — hubhood.xyz

Landing site for **Hubhood**, private liquidity infrastructure. Ticker: **$HUB**.

Static HTML, CSS and vanilla JavaScript — no build step, no dependencies, no framework.
Push it, point Vercel at it, and it's live.

## Structure

```
.
├── index.html            # the whole page (nav, hero, protocol, how it works,
│                         # features, $HUB, roadmap, FAQ, CTA, footer)
├── assets/
│   ├── css/styles.css    # all styling; design tokens live in :root at the top
│   ├── js/main.js        # nav toggle, scroll reveal, counters, copy-CA, FAQ
│   └── img/
│       ├── logo.svg      # logo + favicon
│       └── og.png        # 1200×630 social preview card
├── vercel.json           # clean URLs, security headers, asset caching
├── robots.txt
├── sitemap.xml
└── site.webmanifest
```

## Deploying to Vercel

1. Go to [vercel.com/new](https://vercel.com/new) and import this repository.
2. Framework preset: **Other**. Leave build command and output directory empty —
   this is a plain static site, there is nothing to build.
3. Deploy.
4. In **Project → Settings → Domains**, add `hubhood.xyz` and `www.hubhood.xyz`,
   then set the DNS records Vercel shows you at your registrar.

Local preview — anything that serves a folder works:

```bash
python3 -m http.server 3000     # then open http://localhost:3000
```

## Things to fill in before launch

Search the repo for these and replace them when the details are final:

| What | Where | Current value |
|---|---|---|
| $HUB contract address | `index.html` → `id="copy-ca"`, both the `data-ca` attribute and the `id="ca-text"` label | `TBA — announced at launch` |
| Extra socials (Telegram, Discord, docs) | `index.html` → footer "Community" column and the header | not present yet |

X is already wired to [@hubhood_xyz](https://x.com/hubhood_xyz), and the launch venue
links to [Pons](https://x.com/ponsdotfamily).

## Editing notes

- **Colours and spacing** are CSS custom properties at the top of `assets/css/styles.css`
  (`--accent` is the mint green; change it once and the whole site follows).
- **Any element with `class="reveal"`** fades in on scroll. Add the class to new blocks
  to match, or leave it off for content that should show immediately.
- **Stat counters** animate from the `data-count` attribute, with an optional `data-suffix`.
- The page respects `prefers-reduced-motion`, so all animation is skipped for users who
  ask their OS for less of it.

## Regenerating the social card

`assets/img/og.png` was rendered from an HTML template at 1200×630. To change it, edit the
markup you want, screenshot it at that size, and overwrite the file — the meta tags in
`index.html` already point at the path.

---

Nothing here is financial advice. $HUB is a volatile digital asset; do your own research.
