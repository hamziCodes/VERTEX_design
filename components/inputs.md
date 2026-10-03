# Inputs

## Anatomy

A field is `surface.input`, 1 px `line.boundary`, `radius.sm` (10 px),
height 44 (`layout.touch-min`), padding 12 / 16. Labels sit above the field
(`body-s`, 500). Helper text is `caption` / `text.secondary` below the
field. Placeholder is an example (`you@company.com`), never the name.

## Token mapping

| Part | Token |
|:--|:--|
| Background | `surface.input` |
| Border at rest | `border.boundary` (1 px, Fog Line 3.39:1 / Tide Line 3.06:1) |
| Radius | `radius.sm` |
| Height | 44 px |
| Label | `body-s`, 500, `text.primary` |
| Placeholder | `text.placeholder` at 0.7 opacity |
| Helper | `caption`, `text.secondary` |
| Focus | 2 px `accent.ring` outline at 2 px offset, `:focus-visible` — the boundary does not change colour |
| Invalid | 2 px `border.invalid` **plus** an error message with an icon |
| Error text | `caption`, `feedback.alert.text` |

## States

- **Rest / filled**: boundary border, surface background.
- **Focus**: the focus ring only. Never move the boundary colour.
- **Invalid**: 2 px alert border **plus** message plus icon — never colour
  alone. Errors are announced with `role="alert"` and focus moves to the
  first invalid field.
- **Disabled**: 45% opacity, not focusable, reason nearby.
- **Read-only**: value in `body`, no boundary, no interaction affordance.

## Field types

Checkboxes and radios: 20 px, `radius.xs` (6 px) for checkboxes, pill for
radios, 1 px `line.boundary`, checked fill `accent.fill` with white glyph.
Switches: track `surface.secondary`, knob `surface.primary` on a boundary
ring, on-state track `accent.fill`, `transition.toggle`. Selects and date
pickers use the same chrome as text inputs; dropdowns open with
`transition.menu-open`.

## Do / don't

| Do | Don't |
|:--|:--|
| Label above, visible, with `<label for>` | Placeholder as the label |
| Focus ring on `:focus-visible` | `outline: none` |
| Invalid = border + message + icon | Invalid = red border alone |
| Helper explains the why | Two helpers, one hint, one tooltip |
| Boundary ≥ 3:1 (`line.boundary`) | Hairline or 1.24:1 line as a field edge |
