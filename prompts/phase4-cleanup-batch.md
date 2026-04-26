---
max_turns: 150
---

# 01-relative-url-pages

## What and Why
Phase 4 routed every URL in `_includes/` through `relative_url`, but pages
still mix four URL conventions: leading-slash absolutes, root-relative
paths, parent-relative `../` paths, and the `relative_url` filter. Make
every internal URL on every page go through `{{ '/path' | relative_url }}`
with a leading slash inside the filter — the same convention the includes
already use. This makes the site robust to a future `baseurl` (project
pages, staging path, custom-domain change) and ends the four-conventions
problem.

Treat as a refactor — Boy Scout Rule applies if adjacent cleanup
opportunities show up, but the focus is the URL sweep.

## Scope
Every `.html` page at the repo root and in `lyrics/` and `musings/`. The
sweep covers `<a href>`, `<img src>`, `<source srcset>` (each
comma-separated entry), and any other internal URL. External URLs
(starting `https://`, `http://`, `mailto:`) and Bandcamp/YouTube/Spotify
embed iframes stay unchanged.

## Pattern
- `<img src="/assets/images/foo.jpg">` →
  `<img src="{{ '/assets/images/foo.jpg' | relative_url }}">`
- `<a href="../musings.html">` →
  `<a href="{{ '/musings.html' | relative_url }}">`
- `<a href="lyrics/child.html">` (root-relative) →
  `<a href="{{ '/lyrics/child.html' | relative_url }}">`
- `srcset` entries each get the same wrap, comma-separated as before.

## Done When
- `grep -rE 'href="(/|\.\./)' *.html lyrics/ musings/` returns nothing.
- `grep -rE 'src="(/|\.\./)' *.html lyrics/ musings/` returns nothing.
- `grep -rE 'srcset="(/|\.\./)' *.html lyrics/ musings/` returns nothing.
- `grep -rE 'srcset="[^"]*, (/|\.\./)' *.html lyrics/ musings/` returns
  nothing (catches the second-and-later entries inside srcset).
- `bundle exec jekyll build` succeeds; spot-check that `_site/index.html`,
  `_site/about.html`, `_site/lyrics/child.html`, and
  `_site/musings/the-great-peace-filter.html` still render with working
  asset paths and links.
- Git commit: "Phase 4.5: route page URLs through relative_url"

---

# 02-readme-reconcile

## What and Why
Phase 4 introduced `_data/nav.yml` and Liquid `for` loops in header and
footer. The README still says "no plugins, no data files, no Liquid loops
over hardcoded lists" and instructs contributors to edit
`_includes/header.html` to add a nav item. The README needs to match the
code so the next contributor (human or LLM) follows the right rules.

Treat as a small refactor — keep the README's tone and structure intact,
just update the affected sentences.

## Done When
- The "Conventions" section's "Jekyll for shared HTML only" rule allows
  small data files and the loops they enable (e.g. `_data/nav.yml` driving
  the primary nav). Phrase positively — what is allowed and how it should
  be used — rather than relaxing the old prohibition in place.
- The "Add a new page" section's nav-addition step points at
  `_data/nav.yml`, with the field shape shown (`label`, `href`, `key`).
  The matching `nav_active` value in the page's front matter must equal
  the `key` of the corresponding `nav.yml` entry.
- The "Project layout" tree includes `_data/nav.yml` with a one-line
  description.
- Git commit: "README: reconcile conventions with Phase 4 data-file pattern"

---

# 03-wire-magisches-theater
depends_on: 01-relative-url-pages

## What and Why
Live wildanimalmusic.com has a dedicated Magisches Theater album page;
the local port now has the file (`magisches-theater.html` at the repo
root, pre-built in chat) but `music.html` still links the album title
to bandcamp. Wire the discography link to the new page and stage the
new file if it isn't tracked yet.

Surface depth — do not edit any text inside `magisches-theater.html`.
Verbatim copy from the live site is load-bearing; Phase 2 had a redo
when copy got quietly polished.

## What you'll do
1. Leave `magisches-theater.html` byte-identical to what's on disk.
   Comments inside the file marked TODO (album cover hero, single
   covers) describe optional future image work and are out of scope.
2. In `music.html`, change the Magisches Theater album-title `<h3>`
   link from the bandcamp URL to
   `{{ '/magisches-theater.html' | relative_url }}`. For symmetry, do
   the same for the 2025 self-titled `<h3>` link (target:
   `{{ '/self-titled2025.html' | relative_url }}`). The bandcamp embed
   iframes below each title remain unchanged — they provide streaming.
3. Stage `magisches-theater.html` if `git status` shows it as untracked.

## Done When
- `magisches-theater.html` is tracked at the repo root with no content
  changes from the on-disk version.
- In `music.html`, the Magisches Theater and Self-Titled (2025) `<h3><a>`
  hrefs point at the dedicated pages via `relative_url`. The other three
  album titles (2016, 2019, 2020) keep their bandcamp links — those
  albums have no dedicated page.
- `bundle exec jekyll build` succeeds; `_site/magisches-theater.html`
  renders.
- Git commit: "Port Magisches Theater album page"

---

# 04-content-polish
depends_on: 01-relative-url-pages

## What and Why
Three small content gaps remain vs the live source of truth:

(a) `musings.html` is missing its lede sentence. Live opens with
"Thoughts, musings, and everything in between by John Patrick Therrien"
above the essay listings.

(b) `about.html` shows 6 gallery thumbnails; live shows 8. Source files
`band-photo-09` and `band-photo-10` are already in `_originals/` with
WebP/JPG variants built (1065/800/400). They just need to be wired in.

(c) `self-titled2025.html` uses inline
`style="margin-top: var(--space-7);"` and
`style="margin-top: var(--space-8);"` on the singles `<article>`
elements. Extract to a `.single` class that lives in `styles/main.css`.
The new `magisches-theater.html` already declares `class="single"` on
its singles articles, so no markup change is needed there once the CSS
exists.

Treat as a refactor.

## What you'll do
- `musings.html`: insert
  `<p class="page__lede">Thoughts, musings, and everything in between by John Patrick Therrien</p>`
  immediately after the `<h1 class="page__title">Musings</h1>` line.
- `about.html`: append two `<picture>` blocks to the `.about-gallery`
  div for `band-photo-09` and `band-photo-10`, mirroring the existing
  gallery items' structure (WebP `<source>` with 400w + 800w, JPG
  fallback at 1065w, alt `"Wild Animal — Marie and John Therrien"`,
  `width="1065" height="1065"`). All paths through `relative_url`.
- `self-titled2025.html`: on the two singles `<article>` elements,
  replace the inline `style="margin-top: var(--space-N);"` with
  `class="single"`. Other inline styles on the page (iframe, caption
  paragraph) are out of scope — leave them.
- `styles/main.css`: add
  `.single { margin-top: var(--space-8); }` and
  `.single:first-of-type { margin-top: var(--space-7); }`
  so the rendered spacing matches the existing inline values exactly.

## Done When
- `grep -nE '<article[^>]*style="' *.html` returns nothing.
- `about.html` `.about-gallery` contains 8 `<picture>` blocks (was 6).
- `musings.html` has the lede paragraph between the `<h1>` and the first
  `<article class="essay-listing">`.
- `bundle exec jekyll build` succeeds; visually compare a built
  `_site/self-titled2025.html` before/after — singles spacing should be
  unchanged.
- Git commit: "Polish: musings lede, about gallery 6→8, .single class"
