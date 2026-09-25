# Woodhouse 2.0: Homepage v1 (single direction)

_Sept 25, 2026 · Local file: `pages/home.html` · Online copy: https://claude.ai/artifact/VFQeh4D65w9YAfGQmHkJnD_

## Jesse's decisions after round 2
- Round 2 is much stronger than round 1.
- **Stationery (D)** fits the current Woodhouse aesthetic best. **The Poster (E)** is Jesse's personal favorite, and Jesse may pick and choose elements from The Poster and **The Archive (F)**.
- Three sections stay close to the **original Showit homepage** (Wonder artboard `him`):
  - **Top navigation:** hamburger plus About / Gallery / Blog on the left, WOODHOUSE in the center, social icons on the right, 41px side padding.
  - **Hero:** the original layout, cleaned up. The center title is bigger, the "introducing" script sits right on top of the title, and the hero container uses the same side inset as the nav (41px at 1440).
  - **Heirlooms:** the original centered layout with six polaroids. Four are clearly visible, and the two at the far edges are about 90% off-canvas as a decorative touch.

## How v1 is built
- **Stationery base** for everything else: proof prints, a die-cut newsletter spread, hang-tag service cards, a printed testimonial spread, a photo tucked into an envelope for the style guide.
- **From The Poster:** script words set inline in the caps headlines and "(the veil)" style captions.
- **From The Archive:** the ruled "What sets our days apart" ledger with handwritten lines and a paperclip polaroid, and the safety pin on the testimonial.
- Original copy was brought back where it existed: "A gift for you: Receive my guide for a timeless wedding day", four services (Weddings, Elopements, Events, Destinations), "What sets our days apart" 01–04, "Romantic and effortlessly chic", "Wedding style guide", "Love stories and connections" (a featured post plus three), and "Let's start your chapter".
- Mobile: the heirloom polaroids sit above and below the text with the edge ones still clipped, and the service cards become a swipe carousel.

## Props: SVG, not generated images (decided Sept 25)
- Jesse found the AI-generated prop images (from the asset wishlist) ugly and the page too busy with them. **Decision: draw props as clean inline SVG instead.**
- SVG props: tape strips, paperclip, safety pin, the envelope (open back plus front pocket) and the hang-tag strings.
- Removed completely: paper texture, deckled cards, wax seal, tissue paper, silk ribbon, pressed flowers and the roses.
- The real Woodhouse photos and brand fonts stay.
- The Priority 1 and 2 props in `asset-wishlist.md` are no longer needed. The Priority 3 photos still are.

## Comment round 1 (Sept 25): Jesse's artifact comments, all applied
- **Palette:** back to the grayscale site palette everywhere. White, stone `#f4f4f3`, `#ebebe9` and `#dcdcda` panels, near-black `#0b0b0a` bands, ink `#1c1b19` and muted `#6b665f`. The espresso, taupe, camel and oxblood colors are gone.
- **Heirloom polaroids:** now use Jesse's original frame (`assets/polaroid-frame.webp`, 400×600, photo window at 10.25% / 9.8% / 10.75% / 19.8%).
- **Services:** the gold oval next to the heading is gone, and so is the tab "bump" on each card. The cards are now clothing-style hang tags: chamfered top corners, a punched hole with a ring, and an SVG string.
- **Testimonial:** the Fig. 01 / Fig. 02 thumbnails are gone, and the quote is set in the handwriting script (Thesignature).
- **Featured stories:** the rotating stamp and the names printed over the photos are gone. Each couple's name now sits where "Story Nº __" was.
- **Journal feature card:** no shadow and no fill, just a 1px border.
- **CTA:** rebuilt with no card. White type sits directly on a full-bleed grayscale photo, echoing the hero. It has "Now booking 2027", a script kicker, LET'S START *your* CHAPTER, Inquire, and "Since 2016" / "Made in Austin, TX" in the corners. The label-maker tag is gone.

## Comment round 2 (Sept 25)
- All drop shadows removed (home + about).
- SVG tape replaced by the PNG tapes (`tape-short-1/2.png`, `tape-long.png`).
- Hang tags: gold/bronze metal eyelet; cotton cord drawn as a lark's head through the eyelet, with a teardrop hanging loop, overhand knot and tails (`#hangtag` symbol).
- Testimonial quote now in Nothing You Could Do (Google Fonts, `--font-hand`), because Thesignature wasn't legible at paragraph length. Safety pin removed.
- The gift/newsletter spread was replaced by the Showit Resources "Timeline Guide Section" (`sean.alya`): "A curated guide / Your timeline for a *timeless* wedding day". The tablet mockup is redrawn in CSS (the Wonder PNG has baked-in shadows).

## Open items
- Prices, dates, couple names and the Destinations copy are demo content.
- Next: Jesse reviews the changes, then we roll the design out to the inner pages.
