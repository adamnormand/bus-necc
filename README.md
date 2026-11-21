# normandgroup.com — static site

Rebuild of the Normand Consulting Group WordPress site on the Ohio creative-agency design system (Colabrio demo 4): fixed left rail with vertical logo, full-screen serif menu, "01 // SECTION" labels, two-column section heads, red accent words, stat cards, striped capability discs, platform marquee, light footer. Fonts: DM Serif Display + DM Sans. Plain HTML/CSS, a little JS, no build step.

| File | Purpose |
|---|---|
| `index.html` | Home — hero, intro, three practices, metrics |
| `company.html` | History and philosophy |
| `advisory.html`, `design.html`, `technology.html` | Service pages |
| `publications.html`, `careers.html` | Publications, careers |
| `contact.html` | Offices + mailto form |
| `404.html` | Redirects old WordPress URLs (`/advisory/`, `/company/history/`…) to the new pages |
| `assets/style.css` | Shared stylesheet (colours in `:root`) |
| `favicon.svg` | Favicon |

## To do before cutover
- **Copy the hero photo into the repo.** `index.html` currently points at `https://normandgroup.com/wp-content/uploads/necc_header_tiny_2.jpg`. Save it as `assets/hero.jpg` and change the URL in `index.html`, or it will break when WordPress is shut down.
- Contact form uses `mailto:`. Swap for a Zoho Forms embed if you want submissions captured.
- Publications page links one article back to the WordPress site; migrate it if needed.

## Publish
1. Settings → Pages → Deploy from branch → `main` / root. Preview at `https://adamnormand.github.io/bus-necc/`.
2. When ready: add a `CNAME` file containing `normandgroup.com`, set the custom domain in Settings → Pages, then Enforce HTTPS.

DNS:
```
@    A     185.199.108.153 / 185.199.109.153 / 185.199.110.153 / 185.199.111.153
@    AAAA  2606:50c0:8000::153 / 8001::153 / 8002::153 / 8003::153
www  CNAME adamnormand.github.io
```
Remove old A/CNAME on `@` and `www`. Do not touch MX, TXT/SPF, DKIM (Zoho mail).
