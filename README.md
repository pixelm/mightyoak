# MightyOak Dev Website

Single-page static site. Two files — `index.html` and `mansi.jpg` — that's it. No build step, no framework, no dependencies beyond Google Fonts (loaded from CDN).

## Deploying to GitHub Pages

Since you've already used GitHub Pages for past sites:

1. Create a new repo (e.g. `mightyoak-dev` or use the existing `mightyoak` repo, replacing its contents)
2. Drop `index.html` and `mansi.jpg` in the root
3. Settings → Pages → Source: `main` branch, root folder
4. Wait ~1 min for deploy
5. Point your custom domain (mightyoak.dev or whatever) via Cloudflare DNS, same way you did mansi.cc

## Editing copy

All copy lives directly in `index.html`. Search for the section headers (`<!-- HERO -->`, `<!-- THE WALL -->`, etc.) to find what you want to change. Edit the text between tags. No build step — just save and push.

## Common edits you might want

**Update Calendly link:** search for `calendly.com/mansip/45min` — appears in 3 places (header, hero CTA, closing CTA, footer).

**Change pricing:** search for `1,200` in the pricing section. You'll also want to update mentions of "$1,200" anywhere else in the copy if you change it.

**Swap photo:** replace `mansi.jpg` with a same-named file. Or change the `src` attribute on the `<img>` tag.

**Update email:** search for `mansi@mightyoak.dev` in the footer.

## Notes on the design

- **Typography:** Fraunces (display) + Inter (body) + JetBrains Mono (small labels), all loaded from Google Fonts
- **Color palette:** warm sand background (#F5EFE2), deep ink, deep moss accent (#2E3C2A)
- **Editorial moment:** the "What I believe" section uses Fraunces for body text with a drop cap — intentional change of pace
- **No JavaScript dependencies** except a tiny ~5-line scroll listener for the sticky header border
- **Fully responsive** down to ~360px width
- **Accessibility:** semantic HTML, visible focus outlines, respects `prefers-reduced-motion`

## Performance

- ~24KB HTML (including all inline CSS)
- ~230KB photo (already optimized to 1600px wide, JPEG 88% quality)
- ~3 font files from Google Fonts CDN (cached aggressively)
- No analytics, tracking pixels, or third-party scripts. Add GA4 / Plausible later if you want.

Total page weight under 300KB. Should load instantly on any connection.
