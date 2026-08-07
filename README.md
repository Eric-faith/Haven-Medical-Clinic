# Haven Medical Clinic — Website

Custom-coded, hand-built website for Haven Medical Clinic (Kelowna, BC).
No template, no site builder, no framework — plain HTML5 + CSS3 + a small
amount of vanilla JavaScript (progressive enhancement only; the site is
fully usable with JavaScript disabled).

## Structure

```
index.html       Home
about.html       About Haven / mission / values
services.html    Services + uninsured service fees
team.html        Physician profiles
resources.html   Patient resource links
contact.html     Contact details + enquiry form
```

Each page shares the same header (logo, NAP contact bar, nav) and footer,
duplicated per-file so the site works as plain static HTML with no build
step — just open any `.html` file in a browser.

## Tech notes

- **Fonts:** Montserrat (headings) + Inter (body), loaded from Google Fonts.
- **Images:** the clinic logo and all four physician photos are embedded
  directly as base64 data URIs — nothing to break if hosted images move.
  Location/hero photography is loaded from Unsplash.
- **Mobile nav:** pure CSS (checkbox-driven slide-in drawer) — no JS
  required for the menu to open/close.
- **Animations:** CSS-only entrance/hover/scroll animations; scroll-reveal
  is progressively enhanced with a small IntersectionObserver script that
  degrades gracefully (content stays visible even if JS fails).
- **Colours / type:** driven by CSS custom properties at the top of the
  shared style block in each file (`--primary`, `--accent`, `--dark`, etc.)
  matching the clinic's brand guideline.

## Deploying

No build step needed. Options:

- **GitHub Pages:** push this repo, enable Pages on the `main` branch
  (root), done.
- **Netlify / Vercel:** drag-and-drop the folder, or connect the repo —
  no build command needed, output directory is `/`.
- **Any static host:** upload the six `.html` files as-is.

## Updating content

Each page is self-contained (no shared includes), so a text/content change
needs to be made in every file where it appears (e.g. the footer contact
info repeats on all six pages). This keeps the site dependency-free, at
the cost of some duplication — a fair trade-off for a six-page brochure
site with no CMS.
