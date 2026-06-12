# fitorejaha.com

Jekyll + GitHub Pages. Plain HTML + CSS + Markdown. No SCSS. No JS frameworks.
Live at https://fitorejaha.com/

## Stack
- Jekyll with Liquid templates
- Plain CSS (no preprocessor)
- GitHub Pages deployment

## CSS files
- `css/styles.css` — only active stylesheet
- `css/blog.css` — blog index only, do not touch
- `css/styles_grid.css`, `css/styles_grid2.css` — superseded, leave in place

All visual values are CSS custom properties in :root at the top of styles.css.
Designer tweaks = changes to that block only.

## Units
All sizing in rem/em. No px except:
- `html { font-size: 16px }` — sole anchor
- `1px` borders
- `2px` amber rule element

## Container system
.page-shell — header (nav), all homepage sections, writing index, footer inner
  max-width: var(--container-max)  /* 76rem */
  margin-inline: auto
  padding-inline: var(--margin-outer)
.article-shell — post body text column only
  max-width: var(--container-readable)  /* 44rem */
  margin-inline: auto
.wide-figure — post images wider than article text
  max-width: var(--container-max)
  margin-inline: auto
--margin-outer: clamp(1.25rem, 4vw, 4rem). Never fixed, never overridden per-breakpoint.
--container-max replaces the old --content-max. Do not use --content-max.
Backgrounds stay full-bleed; only content is constrained. Section elements carry
vertical rhythm via padding-block only — never a hardcoded width or horizontal margin.
Dividers: `<div class="section-rule page-shell"><span class="section-rule__line"></span></div>`.

## Colour
--amber: primary CTAs, Read arrows, inline CTAs, hero rule, nav active underline.
--forest: writing row hover only. Invisible at rest.
--ink as background: footer only.
--navy: not in palette. Do not introduce.
Never use --ink at reduced opacity instead of --stone.

## Navigation
Three items: Writing, About, Resume. Do not add or rename.
Nav logo: "Fitore · FJP" (Cormorant serif + Inter sans).
Footer logo: "Fitore" only.

## Content — do not change
City names in journey section: Kosovo, Middle East, New Zealand, Canada.
Principle words: Learning, Translation, Adaptation, Ownership.
Journey subline: "I lived in different places, across four continents. My thinking is influenced by this arc."
All copy, labels, section names, post content: leave exactly as live.
No word "essay"/"essays" in HTML output — use "writing".

## Portrait
/images/portrait-hero.jpeg (.jpeg extension)
No CSS filter. Border on frame wrapper div (.hero__portrait-frame), not img.
~70% column width, centered, padded. object-fit: cover; object-position: center top.

## Career highlights
No dates. No titles. Brand names only.
CURRENTLY → EQ Bank. PREVIOUSLY → Wealthsimple, Wave, CBC / Radio-Canada,
Canadian Digital Service, Vodafone NZ, Global TV, Vancity (inline comma-separated).
No table. No row dividers. No JetBrains Mono in this section.

## Hard rules
- No border-radius anywhere
- No box-shadow
- No gradients
- No animation beyond hover transitions
- No inline styles
- No additional typefaces (Cormorant Garamond, Inter, JetBrains Mono)
- All transitions in @media (prefers-reduced-motion: no-preference)
- No section expands to full viewport width on large monitors — use shell classes
- Do not hardcode any hex colour or rem/px value outside :root

## Scope — do not touch
- _posts/ (any .md file)
- _config.yml
- blog/ directory css (css/blog.css); blog/index.html shares the redesign shells
- css/styles_grid.css, css/styles_grid2.css
- CNAME, Gemfile, LICENSE
- FitoreJahaPrice_Resume2026.pdf

## Assets in /images/
- portrait-hero.jpeg — no CSS filter, amber duotone baked into file
- journey-kosovo.png, journey-jerusalem.png, journey-auckland.png,
  journey-ontario.png — journey-principles, 2:3 ratio
  (place labels read Kosovo / Middle East / New Zealand / Canada)
- F-favicon.ico / F-favicon.png — site favicon
