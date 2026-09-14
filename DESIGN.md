# Meysam Valiolahi — design system

## 1. Concept & identity

A **dark executive** system: charcoal surfaces, warm paper-white text, and a
brass accent — formal, calm, and senior. The layout and copy retain the
site's editorial voice; the visual chrome has been stripped of playful
artifacts (no rotations, no hard offset shadows, no hand-drawn borders). A
quiet echo of the earlier hand-drawn identity survives in the serif display
voice and a single brass full stop. One system serves both languages:
English pages read forward; Persian pages (`body.fa`) are mirrored and use
the local Yekan face. No frameworks, no JavaScript, no external requests.

## 2. Color

Tokens in `assets/site.css`:

- Surfaces: paper `#141412`, deep `#0f0f0d`, card `#1c1c18`
- Text (ink): `#ece7dc`, soft `#b0a893`, faint `#7c7566`
- Lines: `#2a2925`, strong `#3b3931`
- Accents: brass `#c9a44f` (primary, ex-pomegranate token), deep `#b28e3c`,
  sage `#8a9a7b` (secondary, ex-pistachio), gold `#d8b96a` (hover, ex-turmeric)
- Washes: `--wash-pom`, `--wash-pis`, `--wash-tum` — faint tinted panels on
  dark

Brass marks primary actions, focus rings, and emphasis; sage marks
"verified/growth" semantics. Text meets AA contrast on charcoal surfaces.

## 3. Typography

- Display: Georgia / Times serif (48–78px hero) — headlines, pull quotes,
  numerals
- Body: Helvetica-based sans, 17px/1.75
- Persian: local Yekan, 17px/2, headings 1.6 line-height, no tracking
- Dates and card numbers use the mono stack with tabular figures

## 4. Spacing & layout

4px base scale (4→96). Wrap 1080px, reading measure 62ch, purchase panel
660px. Hero is an asymmetric copy/illustration grid. Sections sit between
solid hairline rules; deep stripes alternate `--paper-deep`. Below 900px the
hero stacks; below 600px all grids collapse. Document owns scrolling; no
sticky overlays.

## 5. Components

- **Panel (`.wobble`, `.wobble-soft`)**: card background, 1px hairline border,
  8px radius. The core primitive — calm, no shadows.
- **Sticker**: small lowercase label, hairline border, faint tint; used for
  facts, badges, and bylines.
- **Button link**: brass fill with dark text, ghost (outline) and sage
  variants; 48px minimum height; plain color transitions.
- **Text link**: directional arrow that nudges on hover; mirrors in RTL.
- **Portrait frame (`.polaroid`)**: formal image frame with caption — used
  sparingly.
- **Chapter (experience)**: panel per role with dates, scope, sticker badges,
  and a ✓-stamped wins list.
- **Principle**: ordinal square + prose, no rotation.
- **FAQ**: native details/summary with +/− state, keyboard accessible, no JS.
- **Purchase panel**: card with price, mono account number (LTR-bidi
  isolated), QR disclosure, and gateway/Telegram links. Status pages never
  claim verified payments.

## 6. Illustration

Inline SVG only: the org-chart hero (redrawn for dark — charcoal panels,
brass trunk accents) and the MV monogram favicon. Strokes are 1.4–1.8px;
fills use palette washes. No stock imagery, no generated art, no gradients.

## 7. Motion & interaction

Native anchors and disclosure only. Buttons transition background color on
hover/active. Reduced-motion users get transitions disabled; everything else
works unchanged. No scroll interception, no decorative animation.

## 8. Accessibility constraints

WCAG 2.2 AA target: skip links, landmarks, single h1 per page, focus-visible
outlines (2.5px brass), intrinsic image dimensions, 375px reflow, full
keyboard navigation. Persian pages use `lang=fa dir=rtl`; account numbers and
English labels use bidi isolation. All content renders without JS. No
analytics, cookies, or runtime dependencies. Payment and delivery stay on the
existing external providers (Blue Bank card/QR, Zarinpal gateway, Telegram).

## 9. Files

- `assets/site.css` — the entire system (EN + FA, direction-aware)
- `assets/favicon.svg` — brass MV monogram
- `index.html`, `experience.html`, `perspective.html` — English documents
- `writing/**`, `case-studies/**`, `differently.html` — essays and case study
- `books/**` — Persian book pages sharing the same stylesheet

Manual visual review belongs to the user; automated browser design checks are
explicitly excluded by user instruction.
