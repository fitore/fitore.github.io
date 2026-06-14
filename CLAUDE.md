# fitorejaha.com

Jekyll + GitHub Pages. Plain HTML, Liquid, CSS, Markdown, and small vanilla
JavaScript helpers. No SCSS or JavaScript frameworks.

Live at https://fitorejaha.com/

## Source of truth

- `CLAUDE.md` is the canonical instruction file. Keep `AGENTS.md` as a
  relative symbolic link to it; do not replace it with a separate copy.
- The current implementation is authoritative when an older handoff conflicts
  with these instructions.
- Preserve existing copy, labels, links, and post content unless the user
  explicitly requests a content change.

## Build and verification

- Build with `bundle exec jekyll build`.
- Run `git diff --check` before committing.
- After layout changes, verify the homepage at `http://127.0.0.1:4000/` at
  desktop and mobile widths when a preview server is available.

## CSS files

- `css/styles.css` is the active design-system and layout stylesheet.
- `css/blog.css` is a legacy supplement loaded by `_layouts/default.html`.
  Its old selectors are not used by the redesigned writing pages. Do not
  extend or modify it unless explicitly requested.
- `css/home_layout.css`, `css/styles_grid.css`, and `css/styles_grid2.css` are
  inactive legacy files. Leave them in place and do not modify them.

Add reusable colours, type sizes, spacing, and layout values as custom
properties in `:root` at the top of `css/styles.css`. Component and responsive
rules belong in the relevant section below and should consume those tokens.

## Units

Use rem/em for new sizing. Px exceptions:

- `html { font-size: 16px }` is the sole size anchor.
- `1px` borders.
- The `2px` amber hero rule.

## Container system

`.page-shell` contains the nav, homepage sections, writing index, and footer
inner:

```css
max-width: var(--container-max);
margin-inline: auto;
padding-inline: var(--margin-outer);
```

`.article-shell` contains post body text at `var(--container-readable)`.
`.wide-figure` allows post images to use `var(--container-max)`.

`--margin-outer: clamp(1.25rem, 4vw, 4rem)` is never overridden per breakpoint.
Do not use the removed `--content-max` token. Backgrounds stay full-bleed while
content remains constrained. Section elements carry vertical rhythm through
padding-block, not hardcoded widths or horizontal margins.

Standard divider markup:

```html
<div class="section-rule page-shell"><span class="section-rule__line"></span></div>
```

There is intentionally no divider between Recent Writing and Things I Build.
Keep the visual space above and below Things I Build equal.

## Colour

- `--amber`: primary CTAs, Read arrows, inline CTAs, hero rule, nav active underline.
- `--forest`: writing-row hover only; invisible at rest.
- `--ink` as a background: footer only.
- Navy is not in the palette.
- Use `--stone` for secondary text rather than reduced-opacity `--ink`.
- Things I Build does not use `--amber`.

## Navigation and footer

- Visible nav controls: Writing, Resume, and the dark-mode toggle.
- The mobile hamburger reveals those same controls.
- Do not add an About nav link; the homepage hero retains `id="about"`.
- Nav logo: `Fitore · FJP` using Cormorant serif plus Inter sans.
- Footer logo: `Fitore` only.

## Homepage structure

Keep this order:

1. Hero
2. Four Continents
3. Recent Writing
4. Things I Build
5. Footer

Four Continents:

- Places: Kosovo, Middle East, New Zealand, Canada.
- Principles: Foundations, Translation, Adaptation, Ownership.
- Subline: `I lived in different places, across four continents. My thinking is influenced by this arc.`

Things I Build:

- Two cards, ordered Radian then Colophon.
- Each card: thin top rule, 3:2 image, project name, description, links.
- Titles and descriptions match the Four Continents card text styles.
- Desktop/tablet: two columns with `var(--space-xl)` between them.
- Mobile: one column with Radian first.
- Images and links remain unchanged unless explicitly requested.
- External links use `target="_blank" rel="noopener noreferrer"`.

Use `writing` for site-level navigation and section labels. The approved
Colophon project description intentionally contains the word `essays`; do not
remove or globally replace it.

## Portrait

- Asset: `/images/portrait-hero.jpeg`.
- No CSS filter.
- Border belongs on `.hero__portrait-frame`, not the image.
- Frame is padded and constrained by `--hero-portrait-max`.
- Image uses `object-fit: cover` and `object-position: center top`.

## Career highlights

- No dates or titles; brand names only.
- Currently: EQ Bank.
- Previously: Wealthsimple, Wave, CBC / Radio-Canada, Canadian Digital Service,
  Vodafone NZ, Global TV, Vancity.
- Previous brands remain inline and comma-separated.
- No table, row dividers, or JetBrains Mono.

## Hard visual rules

For new or redesigned components:

- No border radius.
- No box shadow.
- No gradients.
- No image filters or overlays.
- No inline styles.
- No additional typefaces beyond Cormorant Garamond, Inter, and JetBrains Mono.
- No animation beyond hover transitions.
- Put all transitions inside `@media (prefers-reduced-motion: no-preference)`.
- Constrain large-screen sections with shell classes.
- Do not introduce new hardcoded colours or reusable sizing values outside
  `:root`.

Legacy CSS may violate these rules; do not propagate or clean it up unless that
cleanup is explicitly in scope.

## Scope: do not touch without an explicit request

- `_posts/`
- `_config.yml`
- `blog/` and `css/blog.css`
- `css/home_layout.css`, `css/styles_grid.css`, `css/styles_grid2.css`
- `CNAME`, `Gemfile`, `LICENSE`
- `FitoreJahaPrice_Resume2026.pdf`

## Assets in `/images/`

- `portrait-hero.jpeg`: homepage portrait.
- `journey-kosovo.png`, `journey-jerusalem.png`, `journey-auckland.png`,
  `journey-ontario.png`: Four Continents images at 2:3.
- `radian.png`, `colophon.png`: Things I Build images at 3:2; render as-is with
  `object-fit: cover` and centered positioning.
- `F-favicon.ico`, `F-favicon.png`: site favicon.
