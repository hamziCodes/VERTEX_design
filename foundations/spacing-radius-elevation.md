# Spacing, radius, elevation

Tokens: `foundations/tokens.json` → `space.*`, `radius.*`, `shadow.*`,
`border.*`, `layout.*`.

## Spacing

4 px base; scale names are multiples of 4:

`0 / 4 / 8 / 12 / 16 / 20 / 24 / 32 / 40 / 48 / 64 / 80 / 96 / 128`

plus:

- `space.section` — `clamp(80px, 10vw, 160px)` between marketing sections.
  Generous by design.
- `space.gutter` — `clamp(20px, 4vw, 56px)`, the page gutter.

Rules:

- Component internals use the scale (12 / 16 / 24); sections breathe with
  the `section` token. Whitespace is the primary separator — reach for a
  divider only when whitespace cannot do the job.
- Rhythm rule of three: a card's padding, its internal gaps, and its
  distance to the next card should read as 1× / 1× / 2× (e.g. 16 / 16 / 32).
- Never invent a 6, 10, or 14 px gap. If the scale doesn't have it, the
  design doesn't need it.

## Radius

| Token | Value | Use |
|:--|:--|:--|
| `xs` | 6 px | Checkboxes, small chips |
| `sm` | 10 px | Buttons, inputs, small cards |
| `md` | 14 px | Cards |
| `lg` | 20 px | Dialogs, popovers, large cards |
| `xl` | 28 px | Sheets, hero media |
| `pill` | 9999 px | Badges and toggle pills only — not buttons |

Buttons are rounded, not pill — pills are reserved for badges, statuses,
and switches. Corners stay consistent: a card's media shares the card's
radius. Radii do not change between modes.

## Borders

| Token | Value | Use |
|:--|:--|:--|
| `border.hairline` | 1 px solid, `line.hairline` | Decorative dividers |
| `border.boundary` | 1 px solid, `line.boundary` | Fields and controls at rest |
| `border.selected` | 2 px solid, `line.selected` | Selected cards and rows |
| `border.invalid` | 2 px solid, alert solid | Invalid fields |
| `border.focus` | 2 px solid, `accent.ring` | Outline with 2 px offset, `:focus-visible` only |

## Elevation

Cards rest on borders, not shadows. Shadow is for *detachment from the
page*, not decoration. All light shadows are tinted toward Harbor Ink,
never pure black.

| Token | Use | Light | Dark |
|:--|:--|:--|:--|
| `rest` | Cards at rest | none | none |
| `lift` | Hovered / draggable card | 0 8 24 −8, ink 12% | 0 8 24 −8, black 40% |
| `overlay` | Dialogs, popovers, sheets | 0 24 64 −16, ink 18% | 0 24 64 −16, black 55% |
| `pressed` | Inset, segments and switches | inset 0 2 6, ink 10% | inset 0 2 6, black 35% |

There is no "medium" shadow — hover is `lift`, overlays are `overlay`,
nothing else lifts. Never animate `box-shadow`; animate `transform` and
`opacity` instead.

## Layout measures

| Token | Value | Use |
|:--|:--|:--|
| `layout.page-max` | 1200 px | Content column, centred in the gutter |
| `layout.prose-max` | 68ch | Reading measure |
| `layout.nav-h` | 68 px | Top bar height |
| `layout.touch-min` | 44 px | Minimum touch target |
| `layout.form-col` | 560 px | Single-column forms |
| `layout.dialog-max` | 480 px | Dialog width |
| `layout.drawer-w` | 420 px | Drawer width |
| `layout.sidebar-w` | 264 px | App sidebar |
| `layout.sidebar-rail-w` | 64 px | Collapsed rail |
