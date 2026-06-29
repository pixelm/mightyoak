# Mansi — Product & Data Strategist

Static multi-page site, no build step. Drop into any static host (GitHub Pages, Netlify, Vercel, Cloudflare Pages) and it works.

## File structure

```
mansi-site/
├── index.html                                  ← home page
├── mansi-hero.jpg                              ← hero portrait
├── mansi-about.jpg                             ← about portrait
├── README.md
└── writing/
    ├── index.html                              ← writing list page
    └── dont-trust-the-numbers/
        └── index.html                          ← first essay
```

URLs after deployment:
- `/` — home
- `/writing/` — list of essays
- `/writing/dont-trust-the-numbers/` — the first essay

## Adding a new essay

1. Create a new folder under `writing/`, e.g. `writing/new-essay-slug/`
2. Copy `writing/dont-trust-the-numbers/index.html` into it as a starter template
3. Update the title, meta tags, breadcrumb, date, reading time, and body content
4. Add a new entry to `writing/index.html` — copy the existing `.essay-item` block, update title/date/excerpt, point the link to your new slug

That's it. No build step.

## ⚠️ Photos are placeholders

The two photos currently in this folder (`mansi-hero.jpg` and `mansi-about.jpg`) are placeholders — both are the casual portrait from earlier, cropped to vertical. **You'll want to swap these in for your actual professional portraits from the Framer site** before going live.

To swap: just replace those two files (keeping the same filenames). Aspect ratios used:
- Hero photo: 3:4 portrait (tall vertical)
- About photo: 4:5 portrait (slightly less tall)

The actual image dimensions don't have to match exactly — `object-fit: cover` will handle the cropping automatically.

## Deploying to GitHub Pages

1. Create a new repo (or use existing `mightyoak` repo)
2. Drop all three files into the root
3. Settings → Pages → Source: `main` branch, root folder
4. ~1 min later it's live
5. Point your custom domain through DNS

## Editing copy

All copy lives directly in `index.html`. Search for the section comments (`<!-- HERO -->`, `<!-- THE WALL -->`, `<!-- HOW I HELP -->`, etc.) to find what you want to change.

## Common edits

**Calendly link:** search for `calendly.com/mansip/45min` — appears in 3 places (hero button, investment button, footer).

**Pricing:** search for `$3,500` in the investment section.

**Stack list:** search for `class="brand"` to find the tool inventory. Add or remove `<span class="brand">Toolname</span>` lines. They wrap automatically.

**Email:** search for `mansi@mightyoak.dev` in the footer.

## Design notes

- **Color palette:** warm sand background (#F5EFE2), deep ink text, deep moss accent (#2E3C2A). Slightly elevated "what's the wall" and "how I help" sections in a more saturated warm tone.
- **Typography:** Fraunces (display) + Inter (body) + JetBrains Mono (small labels), all loaded from Google Fonts.
- **One editorial italic moment:** the word "systems" in the hero headline is set in Fraunces italic — the single moment of typographic personality in the hero.
- **Two-column layouts:** hero (text left, photo right) and about (photo left, text right) — the asymmetric alternation gives the page visual rhythm.
- **Responsive:** stacks to single column at 880px and below. Fully tested down to ~360px width.

## Sections

1. **Header** — sticky, transparent until scroll
2. **Hero** — two-column with portrait, eyebrow + Fraunces headline + lead + CTA
3. **Stack banner** — typographic row of tools
4. **The wall** — single full-bleed editorial section in Fraunces italic
5. **How I Help** — 6-card grid (Product, Customer, Marketing, Finance, Merchandising, AI)
6. **About** — two-column with second portrait
7. **Working Together** — 4-card grid (Weekly Strategy, Slack, Decision Support, Contractor Bench)
8. **Investment** — centered $3,500/month display + CTA
9. **Footer** — minimal, with email and Calendly link

## Performance

- ~22KB HTML (all CSS inline)
- ~450KB total with both photos (placeholders — your real photos may vary)
- Google Fonts CDN (cached aggressively)
- No JavaScript dependencies beyond a 5-line scroll listener for the sticky header border

Total page weight under 500KB. Loads instantly.
