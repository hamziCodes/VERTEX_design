# Layout, imagery, iconography

## Layout grid

- 12 columns on desktop (`lg`+), 4 on mobile.
- Content column max 1200 px (`layout.page-max`), centred, in the
  `space.gutter`.
- Marketing sections separate by the `space.section` token (80–160 px
  fluid) — whitespace does the separating, not rules or cards.
- App screens: sidebar 264 px (`layout.sidebar-w`, rail 64 px) + fluid
  content; forms in a single 560 px column (`layout.form-col`), one
  question per visual group.

## Whitespace rhythm

- After every section, air. A hero gets a full `section` of space below it
  before the next idea begins.
- Dense tools compress with the scale (8 / 12 / 16) but never below it;
  padding is never asymmetric to "look interesting".
- One idea per section. A section makes its point and hands off to
  whitespace. No bento mosaics, no tile walls, no "everything above the fold".

## The accent audit

Before shipping a screen, select every pixel using an accent token. If it
covers more than 10% of the viewport at 1440 px, remove accent somewhere.
The page should read as neutral with blue moments, not a blue page.

## Imagery

- Real photography only: the team at work, client spaces, products in use,
  the coast in soft natural light. Every image must be traceable to a real
  person, place, or project — ask "who took this and where" before it ships.
- Treatment: honest colour, gentle warm grade, no heavy filters, no
  duotone, no AI-generated faces, no generic handshake/whiteboard stock, no
  3D-render abstract blobs.
- People look at the camera or at their work — never pasted-in "diverse
  team laughing" composites. Caption work with names and roles where the
  subject consents.
- Hero media: photography or a calm product shot on a neutral field — never
  a gradient wash, never a video that autoplays with sound. Video may
  autoplay muted only if it pauses on reduced motion.
- Alt text describes what the image shows ("Ayesha reviewing a Shopify
  storefront with a client in the Lahore studio"), not "image of team".

## Iconography

- Line icons, 1.5 px stroke, round caps and joins, drawn on a 24 px grid,
  `currentColor`. Sizes 16 / 20 / 24 px; never filled and outline mixed in
  one set.
- Icons support labels; they do not replace them. An icon-only button gets
  an `aria-label` and a tooltip.
- Directional icons (arrows, chevrons) flip in RTL. Brand and product marks
  never flip.
- No emoji as UI icons. No icon smaller than 16 px carrying meaning.

## Do / don't

| Do | Don't |
|:--|:--|
| One idea per section, then whitespace | Bento mosaics, tile walls, "everything above the fold" |
| Flat neutrals, one accent, hairline dividers | Gradients, glassmorphism, glows, grain |
| Real photos of real people and work | AI-generated imagery, generic stock |
| Sentence case, plain words, numbers as digits | Title Case Headlines, "leverage", "seamless", exclamation marks |
| Buttons rounded (10 px); pills for badges only | Pill-shaped everything |
| Cards flat on borders; shadow only on hover/overlay | Card-in-card-in-card; shadows as decoration |
| Focus ring visible on every interactive element | `outline: none` |
| Accent < 10% of viewport | Accent backgrounds, accent body text |
| Warm Sand for one band per page, max | Warm Sand buttons, inputs, or whole pages |
| The footer is ink, in both modes | Restyling the footer per page |
