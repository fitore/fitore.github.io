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

## Colour
--amber is the warm accent throughout. Used on:
  primary CTA buttons, READ ESSAY arrows, inline text CTAs,
  hero rule, nav active underline.
--forest: essay row hover only. Invisible at rest.
--ink as background: footer only.
--navy: not in the palette. Do not introduce it.
Never use --ink at reduced opacity in place of --stone.

## Logo
The site logo is "Fitore" — Cormorant Garamond 700.
Update wherever the old monogram appeared, including footer.

## Typography signature
Home display name: Cormorant Garamond 300, 6rem, letter-spacing −0.02em,
line-height 0.96. Do not modify without explicit instruction.
Post title: Cormorant Garamond 300, 3rem desktop / 2rem mobile.

## Journey band
Five vintage travel poster images between hero and essays sections.
Images live in /images/journey-{kosovo,jerusalem,auckland,vancouver,ontario}.png
aspect-ratio: 2/3. No hover states. No lightbox. No interactivity.
Responsive: 5 images desktop → 3 tablet → horizontal scroll mobile.

## Scope — do not touch
- _posts/ (any .md file)
- _config.yml
- blog/ directory
- css/blog.css, css/styles_grid.css, css/styles_grid2.css
- CNAME, Gemfile, LICENSE
- FitoreJahaPrice_Resume2026.pdf

## Assets in /images/
- portrait-hero.jpeg — no CSS filter, amber duotone baked into file
  (NOTE: handover spec'd `.jpg`; actual delivered file is `.jpeg`)
- journey-kosovo.png, journey-jerusalem.png, journey-auckland.png,
  journey-vancouver.png, journey-ontario.png — journey band, 2:3 ratio
Missing asset protocol: leave <!-- ASSET MISSING: filename --> in HTML.
Do not use broken image paths.
