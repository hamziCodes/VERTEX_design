# Parent Studio design system

The canonical design system for the parent/holding studio — the umbrella
over wavia (voice AI), digital marketing, Shopify/e-commerce, motion video,
and social content practices. Visual direction: **Soft Harbor** — neutral,
welcoming, coastal-soft. Version 1.0.0.

This is a name-agnostic system: the company name is still open, so the
voice says "the Studio" until the name is chosen. It is deliberately
distinct from sibling brands (never the vermilion/ember identity) and does
not borrow their colours, motion signatures, or voice.

It is not a brand kit and not a theme. It is a system a designer or a
developer (or an agent) can open and use to build any Studio surface so
that it is structurally and visually Soft Harbor: the right tokens, the
type roles, calm motion, WCAG 2.1 AA.

## The idea in one paragraph

A harbour is a place boats return to: sheltered, orderly, easy to read.
The interface should feel the same — nothing shouts, everything is where
you expect it. Neutrality is a feature: the parent brand never fights the
practices under it. The accent budget is under 10% of any viewport; flat
neutrals carry the page.

## Principles

1. **Welcoming before impressive.** Generous whitespace, sentence case,
   plain words, real faces.
2. **Neutrality is a feature.** Accent under 10% of any viewport; flat
   neutrals carry the page.
3. **Expertise shows, it does not announce.** Numbers, process, real work
   samples — never "world-class" or "cutting-edge".
4. **Flat colour, always.** No gradients, no glassmorphism, no mesh, no
   noise grain. Depth comes from borders, spacing, and one careful shadow.
5. **One idea per section.** A section makes its point and hands off to
   whitespace.
6. **Real photography of real work.** Traceable to a real person, place,
   or project — never generic AI imagery.
7. **Calm motion.** Movement confirms a change of state and then gets out
   of the way. 80–800 ms, no bounce.
8. **Accessible is the baseline.** WCAG 2.1 AA everywhere; measured
   contrast, visible focus, full keyboard path.

## Start here

| You are | Go to |
|:--|:--|
| A designer | `foundations/` — colour, type, spacing, motion, accessibility |
| A developer | `foundations/tokens.json` (the source of truth), then `components/` |
| Checking a screen | `foundations/layout-and-imagery.md` — the accent audit, the do/don't table |
| Writing copy | `foundations/content-voice.md` — microcopy by element, banned words |
| New here | This file, then `CHANGELOG.md` |

## How to use the tokens

`foundations/tokens.json` is the hand-authored source of truth (W3C DTCG
format). Light values are `$value`; dark values live in
`$extensions["studio.modes"].dark`. Aliases use `{path.to.token}`.

```
primitive  ──►  semantic  ──►  component
#5B7A8C         accent.fill     background: var(--sh-accent-fill)
```

Products use the semantic layer only. Custom properties are named `--sh-*`
(`--sh-accent-fill`, `--sh-surface-canvas`, `--sh-text-primary`, …).
Products never use a literal colour, size, or duration — always a token.
A missing token is a design decision waiting to happen, not a reason to
hard-code.

Dark mode: `html.dark`, toggled in-app and remembered in
`localStorage["studio-theme"]`; a pre-paint script sets the class before
first paint. Light (`:root`) is the default. A mode never changes radii,
typefaces, sizes, spacing, motion, layout, or the accent budget.

## Quickstart (a new surface)

1. Read `foundations/color-system.md` — learn the accent budget and the
   accent-contrast rule (light `#5B7A8C` is fills only; text-grade is
   `#3E5C6B`).
2. Read `foundations/typography.md` and `foundations/content-voice.md` —
   sentence case, three faces, no banned words.
3. Lay out with `foundations/layout-and-imagery.md` — 12 columns, one idea
   per section, generous whitespace.
4. Build with `components/` — anatomy, token mapping, states, do/don't for
   buttons, cards, inputs, navigation, badges, dividers.
5. Verify against `foundations/accessibility.md` — it is a build gate.

## Link map

```
README.md · CHANGELOG.md
foundations/
  tokens.json                  W3C DTCG, the source of truth
  color-system.md              palette, semantic mapping, usage rules, modes
  typography.md                Fraunces / Inter / IBM Plex Mono, the scale, rules
  spacing-radius-elevation.md  4px scale, radii, borders, shadows, layout measures
  motion.md                    calm motion, durations, easings, reduced motion
  accessibility.md             WCAG 2.1 AA, measured contrast, the rules
  content-voice.md             tone, mechanics, microcopy, calibration
  layout-and-imagery.md        grid, whitespace, imagery, iconography, do/don't
components/
  buttons.md  cards.md  inputs.md  navigation.md  badges.md  dividers.md
```

## Design language provenance

Built from `workspace/design-language/DESIGN_LANGUAGE.md` (v1.0.0,
2026-10-03), reorganised into this repository. Organisation mirrors the
sibling `CINQ_design` repo (foundations / components / CHANGELOG) as a
structural reference only — no CINQ identity values were carried over.
