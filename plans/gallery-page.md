# Gallery Page Plan

## Goal
Standalone `gallery.html` page, same design language as `index.html`. Linked from nav "Gallery" item (currently dead `#gallery` anchor — no section exists in index.html).

## Design language extracted from index.html
- Fonts: Outfit (body), Cormorant Garamond (headings) — Google Fonts import.
- Colors (CSS vars): `--red:#c41e1e`, `--red-dk:#8b0000`, `--sky:#0284c7`, `--sky-dk:#075985`, `--gold:#d4a017`, greys `--g100..--g900`.
- Fixed blurred nav (70px), pill CTA button, hero with gradient bg + dot pattern.
- Section pattern: `.sec-eyebrow` (colored label) → `.sec-h` (serif heading) → `.divbar` (gradient bar) → `.sec-p`.
- Card pattern: white bg, 1px `--g200` border, radius 12px, shadow, hover lift `translateY(-6px)`.
- `.reveal` / `.reveal.visible` scroll-fade via IntersectionObserver.
- Footer: dark `--g900`, 4-col grid, WhatsApp floating button.
- Existing (unused) gallery CSS classes already in index.html: `.gallery`, `.gal-grid`, `.photo`, `.photo-cap` — reuse these verbatim for visual consistency.

## Images
Extracted 7 images embedded as base64 in index.html into real files under `images/`:
- `coach-sachin.jpg`, `coach-pramod.jpg`, `coach-anubhav.png`, `coach-prashant.jpg`
- `gallery-state-competition.jpg`, `gallery-coaching-session.jpg`, `gallery-group-training.jpg`

index.html left untouched (still uses its own inline base64). Gallery page references the extracted files directly — no duplicate base64 bloat.

## Page structure (gallery.html)
1. `<head>`: same meta/font setup, title "Gallery | Shri Hari Swimming Academy".
2. Shared `<nav>` (same markup, Gallery link bold/active, all links point back to `index.html#section`).
3. Mini page header (reuse `.hero`-style band, shorter, no swimmer/stats — eyebrow + serif `<h1>` + subtext).
4. `.gallery` section with `.gal-grid` of `.photo` cards (image + `.photo-cap` hover caption), pulling the 7 extracted images plus captions (coach portraits, training session, group training, state competition).
5. Shared `<footer>` (same markup/links as index.html).
6. WhatsApp floating button (`.wa`).
7. Reuse `.reveal` + IntersectionObserver script for scroll-fade.

## Follow-up
- Fix nav `#gallery` links in `index.html` (2 spots) to point to `gallery.html` instead of dead anchor.
