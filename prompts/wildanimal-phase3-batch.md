---
max_turns: 100
effort: medium
---

# 01-port-about
effort: medium

## What and Why

Phase 3 — port the about page content. Replace the current stub at `about.html` with the verbatim copy from the live wildanimalmusic.com about page. Use the existing Jekyll layout and design-system primitives (`.section`, `.container`, `.container--narrow`, `.page`, etc.). No new global CSS — if a paragraph needs a different style, use existing utility/primitive classes.

**Critical constraint**: the body text below is the source of truth. Use it verbatim. Do not paraphrase, polish, correct typos, or improve phrasing. The user explicitly does not want CC authoring or editing copy — only marking it up in HTML.

The about page should include a band photo at the top. Use `band-photo-04.jpg` (color, the user identified some are black-and-white) — see `assets/images/MANIFEST.md` for the responsive variants. Use `<picture>` + `srcset` per the existing pattern in `index.html`.

## Body text (use verbatim)

> With a name inspired by exclamatory motifs from a foxy Wes Anderson film, Wild Animal was established to explore themes of being wild in a domestic world. It is our hypothesis that wilderness can be found again, within. Even in the confines of a culture and society which is by its very nature taming. Musically, the guiding principle is to create relatable pop rock music that is nonetheless complex and substantial.
>
> As people, we are **Marie and John Therrien**. A multinational married couple living in Berlin, seeking new ways of embodying spirit which appreciate the beauty of nature, play and visceral as well as contemplative experiences. We hope to bring harmony into this world. Seeking the right balance of consonance and dissonance to move the song.

(The "Marie and John Therrien" was a bold/emphasized inline span on the live site — preserve as `<strong>` or `<em>` to match.)

### Heading: Band Biography

> Wild Animal was formed in 2016 and took off touring. With little to no budget, the first demos were recorded at home in New Orleans, and a tour of the US was planned with the help of a successful kickstarter campaign which bought a school bus for conversion into a tour RV. Over 16,000 kilometers were traveled, and 40+ shows played over two months. With the goal of honing studio skills, John then got a job first as an intern, and eventually as an audio engineer/producer at Music Shed Studios learning from and working with multiple Grammy winning Jack Miele. At Music Shed, the first self-titled studio album was born. Following the personally important opportunity to move to Berlin, John made arrangements to follow up Self-titled with the talented band members Andrew Church and David Gilman before departure. This became impossible when Corona stranded them in southern Louisiana. Thus Acoustic was born. The world had stopped and the studio was empty, so John went everyday, and put together an album alone. Soon after completion, in early 2020 the move to Berlin was made, and Wild Animal's fate was uncertain. However, upon meeting Marie, and playing/writing music together the band found a new life, and Magisches Theater started taking form in late 2022. It was completed in late 2023, and released on July 5th 2024. Late 2024 and early 2025 saw the recording of the latest self-titled album which thematically approaches childhood by keeping the songs relatively short and simple, and asking questions of what's going on with being alive in this society and time.
>
> Before Wild Animal, John found resonance as frontman of Yancellor Chang, a band formed at U.C.S.B. Yance won a battle of the bands, winning a spot at the Extravaganza festival in 2014. The press from this allowed the band to immediately attract local attention, and fostered a favorable run which lasted until the band broke up when the members graduated in 2015.
>
> Marie began her musical journey at the age of 18, lending her voice to a local soul and funk band named "Soulfightazz" in Brandenburg/Germany. Though her professional focus shifted to theater and eventually to becoming a meditation teacher, music remained an integral part of her life.

### Photo credit (small text at bottom)

> Fotos: www.ejafoto.com

## Front matter

```yaml
---
layout: default
title: About
description: About Wild Animal — Marie and John Therrien, an indie pop-rock band in Berlin.
nav_active: about
---
```

## Constraints

- Use verbatim text. Do not paraphrase, polish, correct typos, or improve phrasing.
- Use existing design-system primitives. No new classes added to `styles/main.css` for this page.
- Use `<picture>` + `srcset` for the band photo, reading widths from `assets/images/MANIFEST.md`.
- Don't modify `_layouts/`, `_includes/`, or any other page.

## Done When

- `about.html` rendered cleanly with all body text present verbatim, band photo at top, photo credit at bottom.
- Front matter set correctly.
- No global CSS changes (only `about.html` modified, plus possibly nothing else).
- Git commit: `Phase 3: port about page content`. Pushed to `origin/main`.

---

# 02-port-music
effort: high

## What and Why

Port the music page. This page is third-party-embed-heavy: Bandcamp album players, YouTube videos for "Originals" and "Covers" sections, plus an intro paragraph and Nietzsche quote. Replace the current stub at `music.html` with the verbatim content from the live wildanimalmusic.com music page.

**Critical constraint**: text is verbatim. CC marks up HTML, does not author or edit copy.

## Body text (use verbatim)

### Intro paragraph (top of page)

> A musical exploration of the dichotomy between domestication and wilderness. Putting the question of whether wilderness can be born out of domestic experience to melody, harmony and rhythm.

### Heading: Discography

The discography lists 5 entries. Format each as a clear entry: year, title (the title links to the band's Bandcamp album page), label/format. Below or beside each entry, embed the corresponding Bandcamp player. Use `<iframe>` with the URLs given. Set iframes to `loading="lazy"`, fixed height (`350` for Bandcamp's large player), `width="100%"` (or `width="350"` if you prefer the square small embed; large is what the live site uses), and `style="border: 0;"`.

Discography list (verbatim):

1. **2016 — Neither Predator Nor Prey** | Demos
   - Album page: `https://wildanimal.bandcamp.com/album/neither-predator-nor-prey-demos`
   - Embed: `https://bandcamp.com/EmbeddedPlayer/album=3441137630/size=large/bgcol=ffffff/linkcol=333333/artwork=small/transparent=true/`
2. **2019 — Self-Titled** | Album
   - Album page: `https://wildanimal.bandcamp.com/album/wild-animal`
   - Embed: `https://bandcamp.com/EmbeddedPlayer/album=68290232/size=large/bgcol=ffffff/linkcol=333333/artwork=small/transparent=true/`
3. **2020 — Acoustic** | Album
   - Album page: `https://wildanimal.bandcamp.com/album/acoustic`
   - Embed: `https://bandcamp.com/EmbeddedPlayer/album=1724329660/size=large/bgcol=ffffff/linkcol=333333/artwork=small/transparent=true/`
4. **2024 — Magisches Theater** | Album
   - Album page: `https://wildanimal.bandcamp.com/album/magisches-theater`
   - Embed: `https://bandcamp.com/EmbeddedPlayer/album=1932048747/size=large/bgcol=ffffff/linkcol=333333/artwork=small/transparent=true/`
5. **2025 — Self-Titled** | Album
   - Album page: `https://wildanimal.bandcamp.com/album/wild-animal-2`
   - Embed: `https://bandcamp.com/EmbeddedPlayer/album=1023430753/size=large/bgcol=ffffff/linkcol=333333/artwork=small/transparent=true/`

### Heading: Originals

Three YouTube embeds. Use `<iframe>` with `loading="lazy"`, `width="100%"` or `width="560"`, `height="315"` (16:9), `frameborder="0"` (or `style="border:0;"`), `allowfullscreen`. Wrap iframes in a responsive container div (`.video-embed` or similar — you can scope a small inline `<style>` block in the page if you genuinely need new layout CSS for video aspect-ratio, otherwise use existing primitives).

YouTube IDs (originals):
- `S1INPlWgwvE`
- `q3yvfFJROy4`
- `jvycVIzjCSY`

URLs: `https://www.youtube.com/embed/{ID}` for each.

### Heading: Covers

Three more YouTube embeds, same iframe pattern.

YouTube IDs (covers):
- `Fp9PHORMfNs`
- `DQIMvu_PKaI`
- `CCTIAA3TSRk`

### Closing quote (italics, with attribution)

> *Ohne Musik wäre das Leben ein Irrtum.*
> — Friedrich Nietzsche

Use the existing `.quote` and `.quote cite` styling from `styles/main.css` (used on the homepage Beethoven quote).

## Front matter

```yaml
---
layout: default
title: Music
description: Wild Animal's discography — albums and singles streaming on Bandcamp, with original and cover videos.
nav_active: music
---
```

## Constraints

- Verbatim text. No paraphrasing.
- All third-party iframes need `loading="lazy"` for performance.
- Bandcamp iframes typically need `seamless` attribute and a fallback link below them: `<a href="https://wildanimal.bandcamp.com/album/...">Album Title</a>` so the embed gracefully degrades to a text link if blocked.
- YouTube videos: aspect ratio 16:9 maintained at all viewport widths. If you need a `.video-embed` wrapper class, scope it locally in this file with a `<style>` block in the front-matter content area, or — better — add a single `.video-embed` rule to `styles/main.css` (this is the only file allowed to be modified outside `music.html`, and only for the video-aspect-ratio wrapper).
- Use existing `.quote` and `.quote cite` styling for the Nietzsche quote.

## Done When

- `music.html` has the intro paragraph, discography section with 5 Bandcamp embeds + fallback links, Originals + Covers sections each with 3 YouTube embeds, closing Nietzsche quote.
- All embeds use `loading="lazy"`.
- Front matter set correctly.
- Git commit: `Phase 3: port music page with discography embeds`. Pushed to `origin/main`.

---

# 03-port-lyrics
effort: low

## What and Why

Port the lyrics index page (`lyrics.html`). Three album-specific lyric pages (`lyrics/child.html`, `lyrics/magisches-theater.html`, `lyrics/acoustic.html`) are being committed separately by the user — those are pre-built, complete, with all songs already laid out. Your job is the index page that links to them, plus two "loose" songs from the live site that aren't tied to one of those albums (one from a 2019 album, one a single).

Also: add the CSS classes for `.lyric`, `.lyric__title`, `.lyric__credit`, `.lyric__body`, `.lyric-back`, `.lyric-album-header`, and `.lyric-album-header__year` to `styles/main.css`. The same classes are used by the user's pre-built album pages, so they render consistently.

**Critical constraint**: the two song lyrics below are verbatim. Use them exactly. Do not paraphrase, polish, correct typos, or reflow lines.

## Page structure

The page has two sections:

### Section 1: Album lyrics index

A list of 3 album links. Each link is a card-like entry showing the album title, year, and a "View lyrics" call-to-action. Style with a class like `.lyric-album-link` — minimal, just enough to make each entry feel clickable. Order: newest first.

| Title | Year | Target URL |
|---|---|---|
| Self-titled (Child) | 2025 | `/lyrics/child.html` |
| Magisches Theater | 2024 | `/lyrics/magisches-theater.html` |
| Acoustic | 2020 | `/lyrics/acoustic.html` |

### Section 2: Other songs

Two song blocks, each using the shared `.lyric` markup pattern (matching what's used on the album pages). Structure for each:

```html
<article class="lyric">
  <h2 class="lyric__title">Song Title</h2>
  <p class="lyric__credit">Lyrics: ...</p>
  <pre class="lyric__body">[lyrics, raw newlines preserved]</pre>
</article>
```

Plus a small dateline/source line above or below the credit (your call):
```html
<p class="lyric__source">from Self-titled 2019 aka Dog</p>
```

(or similar `.lyric__source` class — define in CSS too).

### Song 1

Title: **Searching by Wild Animal**
Source: from Self-titled 2019 aka Dog
Credit: Lyrics: John Patrick Therrien

Lyrics (preserve line breaks exactly):

```
Searching for sunshine
On a perfectly climate day
No matter how good I feel
It always goes away
So I'd like to find the source
I am the sort
To believe in
Shangri la la la la la
But I've also been beaten
Felt lost without a job

Meet me there
Please be aware
You'll know it when you see it
Notice when you be it
Allow yourself to feel it
The only control is to let go

Looking out for what I fear I lost
Taking chances
Not worried about price or cost
Seems like a losing fight
But there are those moments
I feel the light
Usually stronger than before
But I'm left so empty
I fall even lower

Meet me there
Please be aware
You'll know it when you see it
Notice when you be it
Allow yourself to feel it
The only control is to let go

Ahhhh
Ahhhh
Ahhhh

Meet me there
Please be aware
You'll know it when you see it
Notice when you be it
Allow yourself to feel it
The only control is to let go
```

### Song 2

Title: **Feelin' Shakey**
Source: Single
Credit: Lyrics: John Patrick Therrien

Lyrics:

```
Well I know that there's something wrong with me
Scratch that
Make it two, three
Infinity

Well don't you know I know I've done you wrong
But I'm not gonna fix it
No, not with this here song

And I'm failing, I'm flailing
Good God I know that I need saving
But Thom and me belong
Oh yes I'm a man
I'm a man of song

And I just can't seem to find
A single person
Who will sing along

So sing along
Sing, sing, sing, sing

But will my love grow?
How the hell should I know
I'll probably be dead too soon
Smoke a joint with George in a dream on the moon
I hope you'll join us
And sing along
Sing along
Sing, sing, sing, sing

My songs have gotten sadder
My body's gotten fatter
All I do is work-play
I can't seem to find the day off
When will it stop

Love may be the only thing that's ever saved my life
But I drown in sorrow worried 'bout tomorrow
With my could be wife

Maybe I'll call up Sturgill
I'll ask him how he does it with his girl
Since that sounds like something he's got right
Right?
Right
I sing Ooo Ooo

Now you know there's something wrong with me
Scratch that, make it two, three
Infinity

Lately she says
"All you do is wrong"
But I can't fix it
No, not with any song
```

## CSS additions to `styles/main.css`

Add a section near the bottom of the file, scoped to lyric-related classes. Approximate spec:

```
.lyric                      — wrapper for one song. Bottom margin around space-7.
.lyric__title               — h2 sizing, fs-xl, tight line-height.
.lyric__credit              — fs-sm, uppercase, tracking-caps, opacity ~0.7. Above body.
.lyric__source              — fs-sm, italic. Above credit (or near it).
.lyric__body                — pre element. Override default monospace: font-family: var(--font-sans).
                              line-height: var(--lh-snug). white-space: pre-wrap.
                              Reset background/border the user agent gives <pre>.
                              fs-md.
.lyric-back                 — small caps link, used at top and bottom of album pages.
.lyric-album-header         — wrapper for the album h1 + year on each album page.
.lyric-album-header__year   — fs-sm, uppercase, tracking-caps, accent color.
.lyric-album-link           — card-like list entry on the index. Make it feel clickable
                              (border, hover lift, accent color on hover). max-width
                              container--narrow already constrains width.
```

Keep additions tight (~50–80 lines of CSS). Use existing tokens — don't introduce new ones.

## Front matter

```yaml
---
layout: default
title: Lyrics
description: Lyrics for songs by Wild Animal — across all albums and singles.
nav_active: lyrics
---
```

## Constraints

- Verbatim lyrics text including line breaks, smart quotes, punctuation, typos.
- Do not write or modify any file at `lyrics/*.html` — those are pre-built and committed by the user separately.
- CSS class names match exactly (`.lyric`, `.lyric__title`, etc.) — the album pages use the same classes.
- No global CSS additions outside the lyric-related classes listed above.

## Done When

- `lyrics.html` has the 3-album index links + 2 loose-song blocks with verbatim lyrics.
- `styles/main.css` has the new lyric-related classes appended at the bottom.
- Front matter set.
- Git commit: `Phase 3: lyrics index page + shared lyric styling`. Pushed to `origin/main`.

---

# 04-restructure-musings
effort: high

## What and Why

Restructure the musings page from a single static page into an index + per-essay subdirectory pattern. The live wildanimalmusic.com musings page currently has 2 essay entries (one a teaser, one "Coming Soon"). Build the index that lists them, plus a `musings/` directory containing 2 individual essay HTML files.

This pattern lets the user add new essays as separate files without touching the index logic — they'll just create `musings/new-essay-slug.html` with appropriate front matter. (Eventually we may auto-generate the index from front matter, but for now hand-maintain it.)

**Critical constraint**: text is verbatim. CC marks up HTML.

## File structure to create

- `musings.html` — index page listing all essays (replaces current stub).
- `musings/` — new directory.
- `musings/the-great-peace-filter.html` — full essay page (currently has only the teaser content; that's all that exists today).
- `musings/between-campbell-and-jung.html` — placeholder essay page ("Coming soon" body).

## Body text (use verbatim)

### Index page (`musings.html`)

Page title: `Musings`. Page intro: just an `<h1>` saying "Musings" — no other intro text on the live site.

Below the heading, list the 2 essays in this exact order (newest first):

**Essay 1**
- Title: `Between Campbell and Jung`
- Date: `Berlin, February 2026`
- Body: `Coming Soon`
- Link target: `musings/between-campbell-and-jung.html`

**Essay 2**
- Title: `The Great Peace Filter`
- Date: `Berlin, January 2026`
- Subtitle (h3 inside the entry): `Where is Everybody?`
- Teaser body (verbatim): `Scientific culture has given a name and structure to the age-old question of whether or not we are cosmically alone in the universe. The Fermi Paradox may read as follows:`
- Pulled-out question (a `<blockquote>` after the teaser): `Given the age and size of the universe, why do we see no evidence of extraterrestrial civilizations?`
- Link text: `Read the full ESSAY`
- Link target: `musings/the-great-peace-filter.html`

Use a `<article class="essay-listing">` wrapper for each entry. If you need to add `.essay-listing` rules to `styles/main.css`, that's allowed — minimal styling for the listing format (date as small caps, title as h2, teaser as body text, "Read full" as a clear CTA link).

### Essay sub-page: `musings/the-great-peace-filter.html`

Full content (verbatim — note this IS all the content on the live site for this essay; it's a teaser-length post for now):

- Title (h1): `The Great Peace Filter`
- Subtitle/dateline (small text below h1): `Berlin, January 2026`
- Subheading (h2): `Where is Everybody?`
- Body paragraph: `Scientific culture has given a name and structure to the age-old question of whether or not we are cosmically alone in the universe. The Fermi Paradox may read as follows:`
- Blockquote: `Given the age and size of the universe, why do we see no evidence of extraterrestrial civilizations?`

A "back to musings" link at the bottom: `← Back to Musings` linking to `../musings.html`.

### Essay sub-page: `musings/between-campbell-and-jung.html`

- Title (h1): `Between Campbell and Jung`
- Subtitle/dateline: `Berlin, February 2026`
- Body: a single paragraph `Coming soon.`
- Back link: `← Back to Musings` to `../musings.html`

## Front matter for sub-pages

Each sub-page front matter (note the `../` prefix needed since these live in `musings/` and reference assets at the repo root):

```yaml
---
layout: default
title: The Great Peace Filter
description: Berlin, January 2026 — an essay on the Fermi Paradox.
permalink: /musings/the-great-peace-filter.html
---
```

(Adjust title/description for the other sub-page.)

**Important**: Jekyll defaults will resolve relative URLs from the page's location, but our header/footer includes use root-relative paths like `assets/...` and `index.html`. Since sub-pages are one directory deeper, those paths break unless we either (a) update includes to use leading-slash paths (`/assets/...`, `/index.html`) — preferred, OR (b) use Jekyll's `relative_url` filter throughout. **Choose (a)**: update `_includes/head.html`, `_includes/header.html`, `_includes/footer.html`, and `_includes/script.html` to use leading-slash paths so they work from any URL depth. This is a one-time fix that benefits any future nested pages too. Test by viewing both `index.html` and `musings/the-great-peace-filter.html` after the build — both should load styles, fonts, images correctly.

### Index page front matter

```yaml
---
layout: default
title: Musings
description: Essays and reflections from Wild Animal — Berlin, ongoing.
nav_active: musings
---
```

## Constraints

- Verbatim text on all entries.
- Update the 4 includes in `_includes/` to use leading-slash absolute paths so nested pages don't break. This is the only modification to `_includes/` allowed in this prompt.
- Add minimal CSS for `.essay-listing` (and `.essay-back` or similar for the back link) to `styles/main.css` — keep additions tight.
- Don't fabricate essay content. The two sub-pages have only what's listed above.

## Done When

- `musings.html` lists both essays with correct dates, titles, teasers/coming-soon, and links to sub-pages.
- `musings/the-great-peace-filter.html` and `musings/between-campbell-and-jung.html` exist with verbatim content + back-link.
- All 4 `_includes/*.html` files updated to use leading-slash paths so they resolve correctly from sub-directories.
- After push and Jekyll build, the homepage still renders correctly AND the new musings/ sub-pages render correctly with full styling.
- Git commit: `Phase 3: restructure musings as index + essay subdirectory`. Pushed to `origin/main`.

---

# 05-port-contact
effort: medium

## What and Why

Port the contact page. Replace the current stub at `contact.html` with a working contact form wired to Formspree, plus the verbatim photo credit, intro line, and Einstein quote from the live site. Use the existing band photo `band-photo-contact.jpg` (already in `_originals/` and `assets/images/`).

**Critical constraint**: text is verbatim. The form HTML is also written by you (CC), but the surrounding copy is verbatim from the source.

## Formspree endpoint

The form posts to this Formspree endpoint. Use it verbatim in the form `action` attribute:

```
https://formspree.io/f/xrerdlga
```

## Body text (use verbatim)

### Photo credit (small text near the photo)

> Foto: www.ejafoto.com

### Heading and intro (above the form)

- `<h1>` or `<h2>`: `Wild Animal`
- Sub-line: `John Patrick and Marie Therrien`

### Form heading

> Get in touch

### Form fields (in this order)

1. **Name** — required. Two sub-fields: `First` and `Last`. Submit field name `name` (combined) or `firstname`/`lastname` separately, your choice — Formspree accepts either.
2. **Email** — required. Field name: `email`. Use `<input type="email">`.
3. **Message** — required. Field name: `message`. Use `<textarea>`.
4. Submit button labeled: `Send`.

Mark required fields with an asterisk indicator. Include a small explanatory line `* Indicates required field` near the top of the form.

Form behavior:
- `method="POST"`, `action="https://formspree.io/f/xrerdlga"`.
- Optional Formspree feature: redirect to a thank-you page on success via a hidden `_next` field. Skip this for now — Formspree's default success page is fine.
- Add `<input type="hidden" name="_subject" value="Wild Animal — new contact form message">` to make incoming emails easier to identify.
- Honeypot anti-spam: `<input type="text" name="_gotcha" style="display:none">` — Formspree convention.

### Closing quote (italics, with attribution)

> *Ich denke oft in Musik. Ich lebe meine Tagträume in der Musik. Ich sehe mein Leben in Termini von Musik.*
> — Albert Einstein

Use existing `.quote` styling.

## Front matter

```yaml
---
layout: default
title: Contact
description: Contact Wild Animal — Marie and John Therrien, Berlin.
nav_active: contact
---
```

## Constraints

- Verbatim text on copy. Form labels can be the natural English/German equivalents shown above.
- Add minimal CSS for form layout to `styles/main.css` — input styling that matches the design system (Oswald font, gold focus ring using existing `--color-accent`, sage or white field backgrounds, generous padding). Keep additions tight (~30 lines of CSS max).
- Form should be styled but not over-engineered: stack fields vertically, full-width on mobile, max-width ~500–600px on desktop.
- Use the band photo as a hero/header image at the top of the page using `<picture>` + `srcset`.
- The Formspree endpoint `https://formspree.io/f/xrerdlga` is the real form action — use it exactly as given.

## Done When

- `contact.html` has the band photo, photo credit, heading + sub-line, the working form (HTML structure complete; endpoint placeholder preserved), and the Einstein quote.
- Form accessibility: labels properly associated with inputs (`<label for="...">`), required fields marked with `aria-required` or `required` attributes.
- CSS additions in `styles/main.css` are minimal and scoped (form-related class names).
- Front matter set.
- Git commit: `Phase 3: port contact page with Formspree-wired form`. Pushed to `origin/main`.

---

# 06-port-self-titled-2025
effort: high

## What and Why

Port the self-titled 2025 album page. This is the most content-dense page on the site: long narrative paragraphs with inline links to Spotify tracks, an album Bandcamp embed, track listing, credits, thanks, and a "Singles" section with two track-by-track entries each with their own Bandcamp embeds and commentary.

The page references two photos already in `_originals/` and `assets/images/`: `self-titled-photo-18.png` and `self-titled-photo-20.png`. Use them with `<picture>` + `srcset` per the existing pattern. (User flagged these may eventually be replaced with higher-quality JPEG versions, but use what's there now.)

**Critical constraint**: text is verbatim. CC does not author or polish copy.

## Body text (use verbatim)

### Top of page

Heading (large, possibly with the album cover image alongside):
> NEW ALBUM OUT NOW

Then four paragraphs of narrative commentary. Words shown as `[link text](URL)` below are inline links — preserve them as italicized linked phrases in the HTML output. The italics on the live site indicate these clickable Spotify track links; render them as `<a href="..."><em>text</em></a>` (or with appropriate inline styling — italic + accent color is the existing pattern).

> This child of ours wants to explore the multi-faceted inclinations and machinations of a fascinating reality. To get started, we'll need a [map](https://open.spotify.com/intl-de/track/08XEul72jiVtSGjAo3znup?si=074eef8c0aed46f3).

> But where is it? And anyways, who's asking? Escape from chaotic self-referencing loops follows from the invocation of a [quiet song](https://open.spotify.com/intl-de/track/6dtu8rsrlFFFmjjCV131gw?si=5644e81578ff4030). Music is indeed a most powerful medicine of self-expression and emotional exploration: easily expelling exasperation.

> Having processed the present prominent needs, pleads of the past persuade us to look at our lack. Isn't it enough? Haven't we arrived? Well, wherever we've landed, it's good to know that they can't [eat](https://open.spotify.com/intl-de/track/1KsaBKS8QA17vcz626gPmc?si=fa70c3eb38a6455d) you. At this point, enough integration has taken place that we can start to look out from within. Whatever it means to have an inside and an outside, greetings are in order: Hello World, DA!, Greetings Earthlings, or maybe, just a simple "[Hey](https://open.spotify.com/intl-de/track/5b72tmoUUvbQ3DliqhLQin?si=8cf3d593de9e493c)".

> If greetings are the simplest extremum on the spectrum of interactions between seemingly separate beings, then the internet must be somewhere on the far side. A vast complexity embodying well the paradox of communication causing separation. Much of society's mental and emotional excrement is exiled from inner and community processes to be caught in the sticky web. Well, [shit](https://open.spotify.com/intl-de/track/2vD99cbg3p60IjVuE0yVn6?si=4d79fd8f77f44004). I guess we'll need to follow the birds to [slip](https://open.spotify.com/intl-de/track/7fh1YgmrJwmZYnDyILYepG?si=4a0cddb9b9124e28) away from this one. The current (2025) counter culture of the world is revising and improving the call for community. The needs are so egregious that there's inevitability in our gathering coherence. Somewhere in the unlaminated liminal spaces between [chaos](https://open.spotify.com/intl-de/track/0Pt0P5ftVnbFFIcf5L4req?si=bc8edf88e1d446a2) and coherence, we must find our way. But of course, having gathered together and evolved from a wide-eyed creature's first awe at awareness to a cohesive community is just the beginning.

> Tomorrow, awsome weather? Or is there a [storm](https://open.spotify.com/intl-de/track/472PIg1vdPSKxu3iUf0OVR?si=d188169044ff42c2) coming?

(Note: "awsome" is a typo on the live site — preserve it verbatim. Do not correct.)

### Main album Bandcamp embed

Below the narrative paragraphs, embed the full album:
- Bandcamp page: `https://wildanimal.bandcamp.com/album/wild-animal-2`
- Embed URL: `https://bandcamp.com/EmbeddedPlayer/album=1023430753/size=large/bgcol=ffffff/linkcol=333333/artwork=small/transparent=true/`
- Fallback link below: `Wild Animal by Wild Animal` → linking to the album page.
- iframe attributes: `loading="lazy"`, `style="border:0;"`, `seamless`, height appropriate for large embed (~470px is typical).

### Heading: Tracks

Track list (just plain list, no links — the inline links above already cover the per-track Spotify links):

1. Lost Map
2. Quiet Song
3. Hey, James
4. Hey
5. Slipstream
6. Shitpost
7. Acoustic Chaos
8. (It's chaos, drop me off)
9. Seelen im Sturm

(Note: track 8 is a parenthetical, possibly a sub-track or interlude name. Preserve the parentheses literally.)

### Heading: Credits

Multi-line, render as a list or paragraph:

> All instruments: John Patrick Therrien
> Male Vocal: John Patrick Therrien
> Female Vocal: Marie Therrien
> Written by John Patrick Therrien and Marie Therrien

A link to lyrics:
> Find all [LYRICS](lyrics.html) here

(On the live site this links to `/lyrics-child.html` which doesn't exist as a page — link to `lyrics.html` which is what we have.)

> Produced, recorded and mastered by John Patrick Therrien
> Album Art: Marie Therrien

### Heading: Thank you!

> Lisa Zwinzscher and Lukas Stodolik: For graciously hosting us at the Schatulle Bömm studio and Gold&Gewitter in Leipzig.
>
> And thank you to our families and friends for their continued support and love.

### Heading: The Singles

Two sub-sections, each with title, Bandcamp embed, and verbatim commentary.

**Single 1: Lost Map**

- Bandcamp embed page: `https://wildanimal.bandcamp.com/album/lost-map`
- Embed URL: (need to derive from page URL — embed pattern is `https://bandcamp.com/EmbeddedPlayer/album={ID}/size=large/bgcol=ffffff/linkcol=333333/artwork=small/transparent=true/`. The album ID for Lost Map isn't in our extraction; if it's not embeddable easily, use a direct link to the Bandcamp page instead of an iframe — that's an acceptable graceful fallback.)
- Fallback link text: `Lost Map von Wild Animal`

Commentary (verbatim):

> In the company of self-reference, strange loops, and the unseen birth of consciousness, this "lost map" tries to chart its own way beyond the Völkergedanken. In mathematics, chaos theory tears an immense hole through any dream of perfectly predicting the natural world. Yet through that rip, a new vision emerges: one where mathematics doesn't describe certainties, but maps families of possibilities, shapes of becoming, the hidden patterns that guide them, and an inevitable pull to have a look for yourself.
>
> This is very powerful indeed, and arguably necessary. A perspective that stands beside the old cathedral of exact solutions without demanding their rigidity, or at least an option on the same level as the tried-and-true method of finding some exact analytical solution, and potentially perturbing it. After all, aren't there enough perturbing things protruding past our placid perspicacity?

**Single 2: Hey, James**

- Bandcamp page: `https://wildanimal.bandcamp.com/album/hey-james`
- Embed: same pattern, ID unknown — same fallback strategy.
- Fallback link text: `Hey, James von Wild Animal`

Commentary (verbatim):

> Imagine a sequel to the James Bond mythos. A situation in which he has finally and fitly retired, finding himself fully in love with a woman who resonates his heart and his interest. With the fight finished, there follows a torrent of past torment; to relax and receive would become his greatest mission. This song is a look at trauma, not just for wounded warriors the world over with misbehaving psychological battle scars, but for those who have experienced trauma of any sort. It's offered as an inspiration; a reminder that "we have everything we need". Also as an invitation to accept and cherish those around us with whom we can experience love. Even in the midst of the most epic battles of our lives, we are complete: finished, whole, and, as part of the totality, fully belonging and loved.

### Photos

Use `self-titled-photo-18` and `self-titled-photo-20` somewhere in the page layout — the live site interleaves them with the narrative. Place one near the top (above or beside the narrative paragraphs) and one further down (e.g., near the Tracks or Singles section). Use `<picture>` + `srcset` per the existing pattern. Read `assets/images/MANIFEST.md` for the actual generated widths.

## Front matter

```yaml
---
layout: default
title: Self-Titled (2025)
description: Wild Animal's 2025 self-titled album — narrative, tracks, credits, and singles.
---
```

(No `nav_active` — this page isn't in the main nav.)

## Constraints

- Verbatim text. Do NOT correct "awsome" or any other typo. Do NOT polish phrasing or sentence-case headings.
- Inline Spotify links: render as italicized linked phrases (`<a><em>...</em></a>`).
- Bandcamp embeds where possible; fallback to text links if the album ID isn't readily derivable.
- Photo placements at sensible breakpoints in the narrative — your choice as long as both photos appear in the page.
- Front matter title: `Self-Titled (2025)` (with parentheses).

## Done When

- `self-titled2025.html` has all narrative paragraphs, all 8 inline Spotify track links, the album Bandcamp embed, the track list (9 entries including the parenthetical), the credits + thanks blocks, the two singles sections each with commentary, and the two album photos.
- All third-party iframes have `loading="lazy"`.
- Front matter set.
- No global CSS additions unless strictly needed for narrative layout (e.g., a `.narrative` class for the long-form intro paragraphs); keep tight.
- Git commit: `Phase 3: port self-titled 2025 album page`. Pushed to `origin/main`.

---

# 07-port-impressum
effort: low

## What and Why

Port the impressum (German legal page). German Impressum requirements are strict — the content must appear verbatim. Replace the current stub at `impressum.html` with the verbatim text from the live site.

**Critical constraint**: text is verbatim. This is a legal document — do NOT translate, summarize, or modify any wording.

## Body text (use verbatim — German)

### Top section

> Copyright: Marie und John Patrick Therrien
> Website (www.wildanimalmusic.de)
> Domain Besitzer: Patrick John Therrien
> Foto: Erika Kopanyiova
> Website made with Weebly

(Note the live site says "Website made with Weebly" — replace this single line with `Website made with GitHub Pages and Jekyll` since we're now hosted there. This is the ONE small substantive change in this port. Everything else is verbatim.)

### Heading: HAFTUNG FÜR INHALTE

> Als Diensteanbieter sind wir gemäß § 7 Abs.1 TMG für eigene Inhalte auf diesen Seiten nach den allgemeinen Gesetzen verantwortlich. Nach §§ 8 bis 10 TMG sind wir als Diensteanbieter jedoch nicht verpflichtet, übermittelte oder gespeicherte fremde Informationen zu überwachen oder nach Umständen zu forschen, die auf eine rechtswidrige Tätigkeit hinweisen.
>
> Verpflichtungen zur Entfernung oder Sperrung der Nutzung von Informationen nach den allgemeinen Gesetzen bleiben hiervon unberührt. Eine diesbezügliche Haftung ist jedoch erst ab dem Zeitpunkt der Kenntnis einer konkreten Rechtsverletzung möglich. Bei Bekanntwerden von entsprechenden Rechtsverletzungen werden wir diese Inhalte umgehend entfernen.

### Heading: HAFTUNG FÜR LINKS

> Unser Angebot enthält Links zu externen Webseiten Dritter, auf deren Inhalte wir keinen Einfluss haben. Deshalb können wir für diese fremden Inhalte auch keine Gewähr übernehmen. Für die Inhalte der verlinkten Seiten ist stets der jeweilige Anbieter oder Betreiber der Seiten verantwortlich. Die verlinkten Seiten wurden zum Zeitpunkt der Verlinkung auf mögliche Rechtsverstöße überprüft. Rechtswidrige Inhalte waren zum Zeitpunkt der Verlinkung nicht erkennbar. Eine permanente inhaltliche Kontrolle der verlinkten Seiten ist jedoch ohne konkrete Anhaltspunkte einer Rechtsverletzung nicht zumutbar. Bei Bekanntwerden von Rechtsverletzungen werden wir derartige Links umgehend entfernen.

### Heading: URHEBERRECHT

> Die durch die Seitenbetreiber erstellten Inhalte und Werke auf diesen Seiten unterliegen dem deutschen Urheberrecht. Die Vervielfältigung, Bearbeitung, Verbreitung und jede Art der Verwertung außerhalb der Grenzen des Urheberrechtes bedürfen der schriftlichen Zustimmung des jeweiligen Autors bzw. Erstellers. Downloads und Kopien dieser Seite sind nur für den privaten, nicht kommerziellen Gebrauch gestattet. Soweit die Inhalte auf dieser Seite nicht vom Betreiber erstellt wurden, werden die Urheberrechte Dritter beachtet. Insbesondere werden Inhalte Dritter als solche gekennzeichnet. Sollten Sie trotzdem auf eine Urheberrechtsverletzung aufmerksam werden, bitten wir um einen entsprechenden Hinweis.
>
> Bei Bekanntwerden von Rechtsverletzungen werden wir derartige Inhalte umgehend entfernen.

### Contact block at bottom

> John Therrien
> Fehmarner Str. 12
> 13353 Berlin
> eMail: [obscured on live site as "[email protected]" — link to /contact.html instead]

For the email line, render as: `eMail: <a href="contact.html">via contact form</a>` since exposing the address as plain text invites scrapers, and the original page also obscured it.

### Final link

> Datenschutzerklärung

This was a link on the live site but didn't go anywhere. Keep it as plain text or skip it — the user's choice. If you keep it, render as plain text (not a link).

## Front matter

```yaml
---
layout: default
title: Impressum
description: Impressum — Wild Animal, Marie und John Patrick Therrien, Berlin.
---
```

(No `nav_active` — Impressum is footer-only.)

## Constraints

- Verbatim German text on all legal sections.
- The ONE change: "Website made with Weebly" → "Website made with GitHub Pages and Jekyll".
- Email: do not expose the actual address; link to the contact form instead.
- Use existing typography. The legal text reads naturally in body-text sizing. Section headings as `<h2>` with the existing styling.

## Done When

- `impressum.html` has all sections (Copyright, Haftung für Inhalte, Haftung für Links, Urheberrecht, contact block) with verbatim German.
- "Weebly" replaced with "GitHub Pages and Jekyll" on the single line.
- Email obscured as a contact-form link.
- Front matter set.
- Git commit: `Phase 3: port impressum page (German legal text verbatim)`. Pushed to `origin/main`.
