# Meysam Valiolahi — design system

## 1. Concept & identity

A **hand-drawn almanac**: warm paper, dotted grid, wobbly ink borders, and
pomegranate-red accents — inspired by human personal sites like Kent C. Dodds',
Maggie Appleton's, and Manuel Moreale's. The goal is a site that feels made by
a person, not generated: first-person copy, hand-drawn SVG illustrations,
slight rotations, honest notes. One system serves both languages: English pages
read forward with square sketch corners; Persian pages (`body.fa`) are mirrored
and use the local Yekan face. No frameworks, no JavaScript, no external
requests.

## 2. Color

Tokens in `assets/site.css`:

- Paper: `#faf6ec`, deep paper `#f3ecdb`, card `#fffdf6`
- Ink: `#2b2118`, soft `#6b5d4d`, faint `#a4937c`
- Lines: `#e2d7c0`, strong dashed rules `#c9b990`
- Accents: pomegranate `#b53a2e` (primary), deep `#8f2c23`, pistachio
  `#6f7d4f`, turmeric `#d9962e`, sky `#4a6d8c`
- Washes: `--wash-pom`, `--wash-pis`, `--wash-tum` for stickers and tints

Pomegranate marks primary actions and emphasis; pistachio marks "growing /
verified" semantics. Text meets AA contrast on paper backgrounds.

## 3. Typography

- Display: Georgia / Times serif (48–78px hero) — reserved for headlines and
  numerals
- Body: Trebuchet-based sans, 17px/1.75
- Hand notes: Comic Sans MS / Chalkboard fallbacks, only for polaroid captions
  and the hero annotation — never for body text
- Persian: local Yekan, 17px/2, headings 1.6 line-height, no tracking
- Dates and card numbers use the mono stack with tabular figures

## 4. Spacing & layout

4px base scale (4→96). Wrap 1080px, reading measure 62ch, purchase panel 660px.
Hero is an asymmetric copy/illustration grid. Sections sit between dashed
"torn paper" rules; deep stripes alternate `--paper-deep`. Below 900px the hero
stacks; below 600px all grids collapse. Document owns scrolling; no sticky
overlays.

## 5. Components

- **Sketch card (`.wobble`, `.wobble-soft`)**: card background, 1.6px ink
  border, irregular hand-drawn border-radius, offset hard shadow. The core
  primitive.
- **Sticker**: small lowercase label with wobbly border and wash background;
  used for facts, badges, and achievements.
- **Button link**: pomegranate fill, ink border, hard offset shadow that
  compresses on press; leaf (pistachio) and ghost variants; 48px minimum
  height.
- **Text link**: directional arrow that nudges on hover; mirrors in RTL.
- **Polaroid**: taped, slightly rotated photo frame with handwritten caption.
- **Chapter (experience)**: sketch card per role with dates, scope, sticker
  badges, and a ✓-stamped wins list.
- **Principle**: rotated ordinal circle + prose.
- **FAQ**: native details/summary with +/− state, keyboard accessible, no JS.
- **Purchase panel**: sketch card with price, mono account number (LTR-bidi
  isolated), QR disclosure, and gateway/Telegram links. Status pages never
  claim verified payments.

## 6. Illustration

Hand-drawn inline SVG only: the org-chart-grows-leaves hero, the pomegranate
favicon. Strokes are 2–2.6px round-capped ink; fills use palette washes. No
stock imagery, no generated art, no decorative gradients.

## 7. Motion & interaction

Native anchors and disclosure only. Buttons nudge on hover and compress on
active. Reduced-motion users get transitions disabled; everything else works
unchanged. No scroll interception, no decorative animation.

## 8. Accessibility constraints

WCAG 2.2 AA target: skip links, landmarks, single h1 per page, focus-visible
outlines (2.5px pomegranate), intrinsic image dimensions, 375px reflow, full
keyboard navigation. Persian pages use `lang=fa dir=rtl`; account numbers and
English labels use bidi isolation. All content renders without JS. No
analytics, cookies, or runtime dependencies. Payment and delivery stay on the
existing external providers (Blue Bank card/QR, Zarinpal gateway, Telegram).

## 9. Files

- `assets/site.css` — the entire system (EN + FA, direction-aware)
- `assets/favicon.svg` — hand-drawn pomegranate
- `index.html`, `experience.html`, `perspective.html` — English documents
- `books/**` — Persian book pages sharing the same stylesheet

Manual visual review belongs to the user; automated browser design checks are
explicitly excluded by user instruction.
