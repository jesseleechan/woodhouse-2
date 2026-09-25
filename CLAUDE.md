# Woodhouse 2.0 — Claude Code guide

Jesse (GlowUp Online) is refreshing **Woodhouse**, a top-selling Squarespace + Showit template sold on Etsy to wedding photographers. Goal: more editorial and premium ("it should look expensive") while keeping the romantic, scrapbook, film/heirloom personality. Demo persona: **Emma Woodhouse**, wedding photographer, "Made in Austin, TX".

Full history lives in `docs/` — read only what the task needs:
- `docs/refresh-context.md` — master brief: brand system, site map, Wonder artboard IDs, asset notes
- `docs/homepage-v1.md` — current homepage decisions + applied comment round
- `docs/homepage-round-1.md`, `docs/homepage-round-2.md` — earlier explorations (A–F)
- `docs/asset-wishlist.md` — photos still wanted

## Folder layout
- `pages/home.html` — **homepage v1, the approved base.** Self-contained HTML/CSS/JS.
- `pages/about.html` — About page v1 (done). Content from Wonder `gift`; its About-only photos load from the Wonder CDN.
- `pages/gallery.html` — Gallery page v1 (done). Content from Wonder `shop`; the six story photos load from the Wonder CDN. Story prints + category filter + CSS "Bridal · Photography" badge + outtakes proof strip.
- `pages/services.html` — Services page v1 (done). Content from Wonder `zip` + Events from the homepage (4 collections). Investment / What’s included accordion copy and prices are demo content matching the homepage tags.
- `pages/process.html` — The Process page v1 (done). Content from Wonder `mens`; the Showit "Celebrating love stories" split-photo banner doubles as the page CTA.
- `pages/mentorship.html` — Mentorship page v1 (done). Content from Wonder `bosn`; second offer renamed "The Woodhouse Mentorship" (fixes the repeated title). Offer prices ($450 / $2,800) and the sixth item in each list are demo content.
- `pages/resources.html` — Resources page v1 (done). Content from Wonder `sean`. Timeline guide, style-guide envelope and journal reuse the homepage sections (CSS copied from home.html — keep them in sync). Newsletter renamed "Letters from Emma" so it doesn't repeat the timeline guide.
- `pages/blog.html` — Blog page v1 (done). Content from Wonder `wine`; six distinct demo posts with a working category filter; reuses the Letters spread, timeline guide and Celebrating banner.
- `pages/contact.html` — Contact page (built from scratch, no Wonder source). Gold oval mirror hero, "Dear Emma" letter-style inquiry form with validation + thank-you state, FAQ, Instagram strip. `contact.html?interest=weddings|elopements|destinations|events|mentorship` preselects the interest; all Inquire / Reserve / pricing-guide / mentorship CTAs link here.
- Former Wonder CDN images now live in `assets/wonder/` (filenames are the CDN hashes).
- `pages/links.html` — Link in Bio page (built from scratch). Standalone (no site nav/footer), mobile-first column; on wide screens a sticky full-height photo sits beside it. Primary link is the homepage hang tag (`#hangtag` sprite copied in). Not linked from the site on purpose; it is the Instagram bio URL.
- `pages/story.html` — Gallery item / single story template (built from scratch): Olivia & Henry, Tuscany. Hero, story + "day at a glance", three photo chapters (duo, wide, side-by-side, taped film-roll trio), credits, previous/next, and a keyboard lightbox. Every Gallery card and homepage Featured Story links here. Couple, vendors and quote are demo content.
- Site is complete as HTML: home, about, gallery, story, services, process, mentorship, resources, blog, contact, links. Still placeholder: individual blog post pages, form endpoints. Still placeholder: blog post pages, form endpoints.
- `assets/` — photos, graphics and prop cutouts (48 files). Referenced as `../assets/<name>` from `pages/`.
- `fonts/` — licensed brand fonts as WOFF (IvyPresto light/regular + italics, Thesignature, Fino Sans). Referenced as `../fonts/<name>.woff`. Do not publish them publicly without checking the web-embedding license.
- `design inspo/` — reference images only; never used on pages.

Preview: open the HTML file in a browser, or run `npx serve .` from this folder. The floating Desktop / Mobile toggle switches to a real 390px container-query layout.

## Brand system
- Fonts (CSS vars): `--font-heading` IvyPresto Display (weight 300, italic for accent words) · `--font-script` Thesignature · `--font-logo` Fino Sans · `--font-body` Inter · `--font-mono` DM Mono (uppercase, tracked, for overlines/labels). Inter and DM Mono come from Google Fonts. Copy the `@font-face` block from `pages/home.html` into new pages.
- Palette (grayscale only — espresso/taupe/oxblood were removed): white, stone `#f4f4f3`, panels `#ebebe9` / `#dcdcda`, near-black `#0b0b0a`, ink `#1c1b19`, muted `#6b665f`. Many photos in B&W.
- Headline pattern: uppercase IvyPresto caps with one script word inline (`<i class="s">…</i>`), e.g. BESPOKE MOMENTS *crafted* WITH LOVE. Mono overline above every heading. Underline-style text links (`.tlink`).
- **No drop shadows** anywhere. Tape = `assets/tape-short-1.png` / `tape-short-2.png` / `tape-long.png`.
- Props are **clean inline SVG** (paperclip, envelope, hang-tag cord + gold eyelet `#hangtag`) — defined as `<symbol>`s in home.html. Jesse rejected the AI-generated prop images as ugly/busy: don't use paper-texture, deckled card, wax seal, tissue, ribbon, pressed flowers or roses webp files.
- Don't overuse polaroids. Heirloom polaroids use `assets/polaroid-frame.webp` (400×600, photo window 10.25% / 9.8% / 10.75% / 19.8%).
- Motion: transforms only, nothing starts hidden, all off under `prefers-reduced-motion`.
- `polaroid-03.jpg` duplicates `journal-garden-window.jpg` — don't use both on one page.

## Homepage v1 structure (keep)
Nav (hamburger + About/Gallery/Blog left, WOODHOUSE centered, socials right, 41px inset) → hero (FROM YES *to* FOREVER, "introducing" script) → heirlooms (6 polaroids, 2 edge ones ~90% off-canvas) → proof strip → timeline guide (from Showit Resources `sean.alya`, CSS tablets) → services as hang-tag cards (Weddings, Elopements, Events, Destinations) → "What sets our days apart" ledger → testimonial (quote in `--font-hand` Nothing You Could Do, no pin) → featured stories → style guide envelope → journal → CTA on full-bleed photo → footer ("01 — Always, Forever — 04").

## Next step
Inner-page rollout is done (About, Gallery, Services, The Process, Mentorship, Resources, Blog). Next: Jesse reviews all pages, then the design moves into Wonder for polish. Content/structure source of truth is the Showit rebuilds in Wonder (see `docs/refresh-context.md` §4 and §6). Reuse the nav, CTA and footer from home.html on every page.

Known copy fixes: Sales page second offer is now "The Woodhouse Mentorship" (fixed in mentorship.html); Home Events description must not reuse Elopements copy. Prices, dates, couple names and Destinations copy are demo content.

## Final workflow
HTML pages here are the design source → final design goes into Wonder for hands-on polish → rebuilt by hand in Showit and Squarespace. A hosted copy also serves as the Etsy live demo.

## Online copies (claude.ai, created in Cowork)
- Homepage v1 artifact: https://claude.ai/artifact/VFQeh4D65w9YAfGQmHkJnD
- Asset Library artifact: https://claude.ai/artifact/RBJbBmqHeFJjdNtwTBxWEY
The local files here are now the working copy.
