# Woodhouse Template Refresh — Project Context

_Last updated: Sept 25, 2026 · Owner: Jesse (GlowUp Online)_

## 1. The goal
Woodhouse is one of GlowUp Online's top-selling Etsy templates, sold for **Squarespace** and **Showit**, for **wedding photographers**. It's about a year old and looks dated, so this is a **Woodhouse 2.0 refresh**: more editorial and premium ("it should look expensive") while keeping the original personality — romantic, a little scrapbook-like and free-flowing in the Showit style, with polaroids, script accents and a film/heirloom mood.

## 2. Workflow
Neither Wonder nor HTML exports to Showit or Squarespace, so the final template is rebuilt by hand on each platform.
1. Explore homepage directions as HTML (done: rounds 1 and 2).
2. Roll the winning direction out to the inner pages as HTML: About, Gallery, Services, The Process, Mentorship/Sales, Resources, Blog. (done Sept 25: `pages/*.html`)
3. **← current step** Bring the final design into Wonder for hands-on polish; Wonder becomes the build reference for Showit and Squarespace.
4. Keep a hosted HTML version as the public live demo linked from the Etsy listings.

## 3. Brand system
**Fonts:** Headings IvyPresto Display incl. italic (`--font-heading`) · Script accents Thesignature (`--font-script`) · Logo Fino Sans · Body Inter (`--font-body`) · Labels DM Mono, uppercase, tracked (`--font-mono`). Licensed originals: `C:\Users\trevo\Downloads\woodhouse fonts`; WOFF copies in `fonts/`. Check licenses allow web embedding before anything goes public.

**Colors:** ink `#1c1b19`, muted `#6B665F`, stone `#f4f4f3`, near-black `#0b0b0a`, white; photos often B&W.

**Signature motifs:** tilted/scattered polaroids · script kickers ("make magic happen.", "let me be your storyteller", "where romance meets film") · headlines mixing an italic/script word ("FROM YES *to* FOREVER", "CRAFTED *with* LOVE", "THE SOUL *of* OUR DAY") · circular "Bridal Photography" badge · envelope free-download opt-in · gold oval frame · mono overlines above every heading · underline text buttons · footer with nav both sides, centered logo, "01 — Always, Forever — 04".

**Voice:** warm, romantic, literary — heirlooms, novels, film. Persona **Emma Woodhouse**, "made in Austin, TX".

## 4. Wonder
File **Woodhouse**, page **"Showit"** (pageId `01a0d5c8-f44b-72b1-87ed-1a2b5b32fc98`). Clean Showit rebuilds (1440px, flex, at x=5640) are the source of truth for content and structure:

| Page | Artboard ID | Original import |
|---|---|---|
| Home | `him` | `ket` |
| Gallery | `shop` | `mud` |
| About | `gift` | `vol` |
| Blog | `wine` | `psp` |
| Resources | `sean` | `nib` |
| Sales Page (mentorship) | `bosn` | `funk` |
| The Process | `mens` | `wugg` |
| Services | `zip` | `tag` |

Shared blocks on Services (`zip`): Nav `zip.eur`, Final CTA `zip.ore`, Footer `zip.dir`. Pull full page copy with Wonder `get_element_code` on these artboard IDs.

Page "Squarespace" also has older rebuilds: "Page - Home Editorial" (`fid`), "Page - Home Editorial Signature" (`dug` — filmstrip, taped polaroids, arch-topped Featured Stories, envelope style guide), "Page - Home Motion" (`zum`), "Motion Storyboard" (`roi`). Motion prototype: https://claude.ai/artifact/MGgyGg8Wbieja21KMjskYb

**Wonder gotchas:** set images with `bg-[url(...)] bg-cover bg-center bg-no-repeat`; absolute layers need `size-full inset-0 absolute`. `duplicate_elements` className overrides don't reliably change background images — duplicate first, then edit. Each duplicate returns the full artboard tree (expensive on big pages) — add nav/CTA/footer early. Max four screenshots per artboard; call `finish_artboard` and `finish_session` after edits.

## 5. Assets (`assets/`)
**Graphics:** `woodhouse-wordmark.webp`, `polaroid-frame.webp`, `gold-mirror-frame.webp` (oval opening ≈ left 13%, top 12%, 73.4% × 75.2%), `envelope.webp`, `roses.webp`, `note-card.webp`.

**Photos:** `hero-field-couple.jpg` (wide, couple small in frame), `cta-embrace.jpg`, `style-guide-backdrop.jpg`, `mirror-couple.jpg`, `testimonial-couple.jpg`; filmstrip `film-veil-beach/running/cake/coast.jpg`; stories `story-car-kiss/veil/hand-kiss.jpg`; journal `journal-bouquet-kiss/centrepieces/garden-window.jpg`; `polaroid-01…08.jpg`. `polaroid-03` = `journal-garden-window` (duplicate).

**Rejected AI props** (kept in folder, don't use): card-deckled, paper-texture, tissue-paper, torn-paper-edge, safety-pin, paperclip-silver, pearl-pin, tape-01/02/03, ribbon-silk, pressed-flowers, wax-seal, dymo-tape, stamp-ink, negative-strip, polaroid-tall, envelope-cream-open/front.

**Wonder CDN** (`https://cdn.wonder.so/images/01a0d496-94f4-7695-b8db-45a15499407c/<filename>`), not yet local:
- Tall Showit polaroid frame: `d41055a3c975c7c89a9fc71b5d0ce564ca31fddc028d582f57f73d7594edb8c3.png` (photo clip ≈ `inset(6% 7% 22% 7%)`)
- Bridal Photography badge: `5ff460f5a9e83acf1c0f9a0b4042cab7526627bd40d2c1d9b6ba4f1cd7a2e5b4.png`
- Tablet mockup (timeline guide): `67650032aa44069d1e71baa80376831f96334a58f9466fc2a373bee6f8757f35.png`
- Footer logo: `edfd60a1099dd7463759f2eafa86d41d0115b54e7c72af6e09d209fb2d42ccea.png`
- About hero, newsletter, villa table, B&W flowers and gallery photos — full filenames are in the rebuild artboards' code.

## 6. Site map (current Showit version)
**Home:** hero "introducing / FROM YES *to* FOREVER" · "More than photographs, they're heirlooms" + polaroids · B&W four-photo strip · "Bespoke moments crafted *with* love" services · newsletter · "What sets our days apart" 01–04 · testimonial "She captured the soul *of* our day" · featured stories · envelope style guide · journal · CTA · footer.

**About:** "A storyteller for the wildly in love", "Timeless imagery for the modern romantic", "When I'm not behind camera" favorites list.
**Gallery:** "A curated collection of love stories", grid of six polaroids.
**The Process:** "Heart-first, lens ready", "Rooted in connection & artistry", steps 01–04, "Magic in every moment".
**Sales / Mentorship:** "Wedding photography coaching", the Clarity & Action Session, "We will be a perfect fit if…".
**Resources:** free guides (timeline guide, engagement style guide), journal, newsletter.
**Blog:** category filter, featured story, latest stories.

**Copy fixes for 2.0:** Sales page repeats "Clarity & Action Session" for its second offer; Home "Events" reused the Elopements description (fixed in v1).

## 7. Direction notes
- Keep the original personality; the old "Signature" variation (filmstrip, taped polaroids, envelope style guide) was a favorite.
- Don't overuse polaroids (Featured Stories moved to other card shapes for that reason).
- Aim for free-flowing, rhythmic, scrapbook Showit energy with editorial restraint.
- Motion explored: scroll-driven reveals, sticky/pinned sections, clip-path reveals, layered crossfades, varied section pacing.
- Inspiration folder added: paper objects over photos, giant serif caps with photos cutting through and inline script words, desk props, typewriter-style mono copy, hand-ruled tables, arches with concave notches.
