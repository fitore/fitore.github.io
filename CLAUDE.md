# fitorejaha.com

Jekyll + GitHub Pages. Plain HTML + CSS + Markdown. No SCSS. No JS frameworks.

## Stack
- Jekyll with Liquid templates
- Plain CSS (no preprocessor)
- GitHub Pages deployment

## CSS files
- `css/styles.css` — active stylesheet for home page + post layout
- `css/blog.css` — blog index pages only, do not touch
- `css/styles_grid.css`, `css/styles_grid2.css` — superseded, leave in place

All visual values are CSS custom properties in the `:root` block at the top
of `css/styles.css`. Designer tweaks = changes to that block only.

## Units
All sizing in rem/em. No px except:
- `html { font-size: 16px }` — the sole anchor
- `1px` borders
- `2px` amber rule element

Violation = a hardcoded value that breaks on user font-size changes.

## Hard rules
- No border-radius anywhere
- No box-shadow
- No gradients
- No animation beyond hover transitions (colour shifts only)
- No additional typefaces (three loaded: Cormorant Garamond, Inter, JetBrains Mono)
- No inline styles
- All transitions in @media (prefers-reduced-motion: no-preference)
- No CSS filter on portrait image (duotone is baked into image file)
- Portrait does not bleed to viewport edge — ~70% column width, centered, padded
- Portrait border is on the frame wrapper div (.hero__portrait-frame), not the img
- No word "essay" or "essays" in any HTML output — use "writing" throughout
- Post body is centered (margin auto) on large screens, not flush left

## Colour
--amber is the warm accent throughout. Used on:
  primary CTA buttons, READ → arrows on writing rows, inline text CTAs,
  hero rule, nav active underline.
--forest: writing row hover only. Invisible at rest.
--ink as background: footer only.
--navy: not in the palette. Do not introduce it.
Never use --ink at reduced opacity in place of --stone.

## Footer links
Three links only: LINKEDIN, X, RESUME.
RESUME links to /FitoreJahaPrice_Resume2026.pdf, target="_blank".
No CONTACT link in the footer.

## Logo
Nav logo: "Fitore · FJP"
  - "Fitore": Cormorant Garamond 700, 1.125rem, --ink
  - "·": Inter 400, --stone, margin 0 0.3em
  - "FJP": Inter 500, var(--text-meta), 0.1em tracked, uppercase, --stone
Footer logo: "Fitore" only — no FJP in footer.

## Career highlights
No dates. No titles. Brand names only.
Two groups with spaced-caps labels:
  CURRENTLY → EQ Bank (own line, --ink weight 500)
  PREVIOUSLY → Wealthsimple, Wave, CBC / Radio-Canada, Canadian Digital
               Service, Vodafone NZ, Global TV, Vancity
               (inline comma-separated, --stone weight 400)
No table. No row dividers. No JetBrains Mono for this section.

## Typography signature
Home display name: Cormorant Garamond 300, 6rem, letter-spacing −0.02em,
line-height 0.96. Do not modify without explicit instruction.
Post title: Cormorant Garamond 300, 3rem desktop / 2rem mobile.

## journey-principles section
Replaces both the former journey band AND the former what-guides-my-work section.
Do not create either of those as separate sections.
Four images only: Kosovo (Learning), Jerusalem (Translation),
Auckland (Ownership), Ontario (Adaptation).
journey-vancouver.png is not used. Do not reference it.
Arc copy above grid: "Four places. The thinking they made necessary."
Each column: image → principle word → description → place name.
aspect-ratio: 2/3 enforced on all images.
Responsive: 4 columns → 2×2 → single column stacked.
No hover states. No lightbox. No interactivity.

## Scope — do not touch
- _posts/ (any .md file)
- _config.yml
- css/blog.css, css/styles_grid.css, css/styles_grid2.css
- CNAME, Gemfile, LICENSE
- FitoreJahaPrice_Resume2026.pdf
(blog/index.html is in scope: it shares the redesign — writing list, no "essay" wording)

## Assets in /images/
- portrait-hero.jpeg — no CSS filter, amber duotone baked into file
  (NOTE: handover spec'd `.jpg`; actual delivered file is `.jpeg`)
- journey-kosovo.png, journey-jerusalem.png,
  journey-auckland.png, journey-ontario.png — 2:3 ratio
- F-favicon.ico / F-favicon.png — site favicon
Missing asset protocol: leave <!-- ASSET MISSING: filename --> in HTML.
Do not use broken image paths.
