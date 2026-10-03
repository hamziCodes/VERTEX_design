# Colour system — Soft Harbor

Tokens: `foundations/tokens.json` → `color.*`. Light is the default mode;
dark is an opt-in equal citizen. Every semantic token resolves in both
modes; a product must never show a light-only hex in dark mode.

## 1. Layers

```
primitive  ──►  semantic  ──►  component
#5B7A8C         accent.fill     .btn-primary { background: var(--sh-accent-fill) }
```

Primitives are named after the harbour (`harbor-mist`, `driftwood`,
`abyss`, `foam`, `gull`, …) so they read as ours. Products touch only the
semantic layer. A product that names a primitive or a literal hex has found
a missing token, not a licence to hard-code — add the token instead.

## 2. Palette

### Light (default)

| Name | Hex | Role | Contrast on canvas |
|:--|:--|:--|:--|
| Harbor Mist | `#F4F6F7` | Page background | — |
| White | `#FFFFFF` | Cards, dialogs, fields | — |
| Still | `#E9EFF2` | Sunken panels, input wells, table bodies | — |
| Warm Sand | `#F1ECE4` | Alternate band, sparing | fg 12.45:1 |
| Driftwood | `#D8DFE4` | Decorative hairlines | decorative (1.24:1) |
| Fog Line | `#768893` | Field / control boundaries | 3.39:1 |
| Harbor Ink | `#1E2A33` | Primary text | 13.51:1 |
| Harbor Slate | `#5B6F7B` | Secondary text | 4.84:1 |
| Harbor Blue (accent) | `#5B7A8C` | Fills, selected states — never body text | 4.20:1 (graphics) |
| Harbor Blue Deep | `#486575` | Accent hover / pressed | — |
| Harbor Blue Ink | `#3E5C6B` | **The text-grade accent** — links, accent text | 6.57:1 |

### Dark

| Name | Hex | Role | Contrast on canvas |
|:--|:--|:--|:--|
| Abyss | `#131D25` | Page background | — |
| Deep | `#1B2833` | Cards, dialogs | — |
| Trench | `#243443` | Sunken panels, fields | — |
| Reef | `#2F414F` | Decorative hairlines | decorative (1.62:1) |
| Tide Line | `#546B7A` | Field / control boundaries | 3.06:1 |
| Foam | `#E9EFF3` | Primary text | 14.72:1 |
| Spray | `#9AADBA` | Secondary text | 7.37:1 |
| Gull (accent) | `#82A5B6` | Fills — **and accent text** (6.51:1) | 6.51:1 |
| Gull Lift | `#96B7C7` | Accent hover | — |

### Feedback (both modes)

| Name | Light | Dark | Rule |
|:--|:--|:--|:--|
| Success | `#3E7C5B` (4.57:1) | `#6FAE8A` (6.58:1) | Text always on tinted bg or as icon; white-on-solid both modes |
| Alert | `#B4543F` (4.53:1) | `#D08675` (5.97:1) | Same as success |
| Info | Harbor Blue family | Gull family | Reuses the accent hue |
| Verify | `#4E7A8C` solid / `#3E5C6B` text in light | `#7A9DAD` (5.90:1) | Body never in `#4E7A8C` (4.32:1) — use `#3E5C6B` |

Dark semantic values are lightened ~25 points against the dark canvas.
Never reuse a light semantic hex in dark mode.

## 3. Semantic mapping

| Product surface | Light | Dark |
|:--|:--|:--|
| Page (`surface.canvas`) | `#F4F6F7` | `#131D25` |
| Card, panel (`surface.primary`) | `#FFFFFF` | `#1B2833` |
| Sunken panel, input well (`surface.secondary`) | `#E9EFF2` | `#243443` |
| Dialog, sheet (`surface.overlay`) | `#FFFFFF` | `#1B2833` |
| Field at rest (`surface.input`) | `#FFFFFF` | `#243443` |
| Tooltip, ink slab (`surface.inverse`) | `#1E2A33` | `#E9EFF3` |
| Alternate band (`surface.warm`) | `#F1ECE4` | `#243443` |
| Dialog scrim (`surface.scrim`) | ink 45% | black 55% |
| Primary text (`text.primary`) | `#1E2A33` | `#E9EFF3` |
| Secondary text (`text.secondary`) | `#5B6F7B` | `#9AADBA` |
| Accent text (`text.accent`) | `#3E5C6B` | `#82A5B6` |
| Text on fills (`text.inverse`) | `#FFFFFF` | `#131D25` |
| Links (`text.link`) | `#3E5C6B` | `#82A5B6` |
| Primary fill (`accent.fill`) | `#5B7A8C` | `#82A5B6` |
| Fill hover (`accent.hover`) | `#486575` | `#96B7C7` |
| Soft highlight (`accent.soft`) | harbor-blue 10% | gull 14% |
| Focus ring (`accent.ring`) | `#5B7A8C` | `#82A5B6` |
| Decorative divider (`line.hairline`) | `#D8DFE4` | `#2F414F` |
| Control boundary (`line.boundary`) | `#768893` | `#546B7A` |
| Selected boundary (`line.selected`) | accent fill | accent fill |

## 4. Usage rules

1. **The accent budget: < 10% of any viewport.** Count every
   `accent.fill`, tint, and blue icon. Primary buttons, one selected state,
   the active nav marker, the logo — and then stop.
2. **Never body text in `accent.fill`.** In light mode the fill is 4.20:1;
   body text in it fails AA. Accent-coloured text is always
   `text.accent` (`#3E5C6B` light, `#82A5B6` dark). Dark's `#82A5B6` is
   text-safe (6.51:1); light's `#5B7A8C` is not.
3. **Warm Sand is an occasion, not a habit.** One alternate band per page
   maximum (e.g. the testimonial band or the CTA band — not both). Never for
   interactive controls; secondary text on it is borderline (4.46:1), so use
   primary text only, or large text.
4. **Flat colour only.** No gradients, no glassmorphism, no shadows-as-colour.
   A legibility scrim over photography is a single flat alpha, not a gradient.
5. **Hairlines are decorative.** Driftwood/Reef dividers (1.24:1 / 1.62:1)
   separate visually, never carry meaning. Anything a control's boundary —
   fields, checkboxes, radios, switches — uses `line.boundary`
   (`#768893` / `#546B7A`, ≥ 3:1).
6. **One hue family for feedback.** Success, alert, verify, and info are the
   only non-neutral hues. Charts use the fixed order in `chart.*`; never
   invent a sixth colour for a series.
7. **The footer is ink in both modes.** Background Harbor Ink
   (`#1E2A33`), primary text Foam (`#E9EFF3`), secondary Spray
   (`#9AADBA`), dividers Reef at 10%. Dark mode does not restyle the footer.
8. **Mode parity.** Every semantic token resolves in both modes.
   `color-scheme` follows the mode so native controls and scrollbars match.

## 5. Mode mechanics

| Mode | Selector | Trigger |
|:--|:--|:--|
| Light (default) | `:root` | The brand. First paint. |
| Dark | `html.dark` | In-app toggle, remembered in `localStorage["studio-theme"]` |

A mode may not change radii, typefaces, sizes, spacing, motion, layout, or
the accent budget. A pre-paint script sets the class from
`localStorage` before first paint (no flash). Dark mode does not follow the
OS; the toggle is explicit.
