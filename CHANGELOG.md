# Changelog

Newest first. Sections: Added, Changed, Deprecated, Removed, Fixed,
Decisions.

## 1.0.0 · 3 Oct 2026

The Parent Studio design system: Soft Harbor identity, name-agnostic
("the Studio" until the company name is chosen). Light-first, dark as an
equal citizen. Deliberately distinct from sibling brands — never the
vermilion/ember identity.

### Added
- `foundations/tokens.json`, W3C DTCG (`$schema:
  https://tr.designtokens.org/format/`), the only hand-authored token file:
  `color.primitive` (28 raw colours) → `color.semantic` (surface, text,
  accent, line, interaction, feedback, chart), `font`, `typography`
  (composite roles), `space`, `radius`, `border`, `shadow`, `blur`,
  `opacity`, `z-index`, `breakpoint`, `layout`, `duration`, `easing`,
  `transition`, `travel`. Light values in `$value`; dark values in
  `$extensions.studio.modes`.
- `foundations/color-system.md`: the two palettes with measured contrast,
  the semantic mapping table, the eight usage rules (accent budget < 10%,
  no body text in the fill, Warm Sand as an occasion, flat colour only,
  decorative hairlines, one hue family for feedback, the ink footer, mode
  parity), mode mechanics (`:root` / `html.dark`, `localStorage["studio-theme"]`).
- `foundations/typography.md`: Fraunces (display) / Inter (body) / IBM Plex
  Mono (labels, kickers, code, IDs), the full role scale, loading rules,
  usage rules (sentence case, one display face per screen, tabular numerals,
  en-PK money and date formats, Urdu Nastaliq/Naskh).
- `foundations/spacing-radius-elevation.md`: the 4 px scale plus `section`
  and `gutter`, the radius set (buttons 10 px, never pill; pills for badges
  only), the four borders, the flat-by-default shadow table (rest / lift /
  overlay / pressed), the layout measures.
- `foundations/motion.md`: six calm-motion principles, the 80–800 ms
  duration scale, the house `ease-out` curve, the named component
  transitions, the reduced-motion contract (1 ms durations, complete page).
- `foundations/accessibility.md`: WCAG 2.1 AA build gate, the measured
  contrast table, the accent contrast rule (light `#5B7A8C` is 4.20:1 — not
  for body text; text-grade is `#3E5C6B` 6.57:1; dark `#82A5B6` is text-safe
  6.51:1), the twelve rules (focus, touch targets, names, errors, overlays,
  keyboard path, zoom, forced colours, reduced motion, no colour-only
  state, live regions, images).
- `foundations/content-voice.md`: the welcoming-expert tone, mechanics
  (sentence case, banned words, en-PK formats), microcopy by element, the
  before/after calibration table.
- `foundations/layout-and-imagery.md`: the 12/4 grid, whitespace rhythm,
  the accent audit, real-photography rules, the line-icon spec, the
  do/don't table.
- `components/`: six principle docs in one fixed format — anatomy, token
  mapping, states, do/don't — for `buttons.md`, `cards.md`, `inputs.md`,
  `navigation.md`, `badges.md`, `dividers.md`.

### Decisions
- Tokens are the source of truth; prose explains intent. When they
  disagree, fix the prose — or change the token deliberately, in the open,
  with the contrast re-measured.
- Light is the default mode. Dark mode does not follow the OS; the toggle
  is explicit and remembered.
- The footer is ink in both modes.
