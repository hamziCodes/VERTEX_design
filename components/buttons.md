# Buttons

## Anatomy

A button is the `button` type (Inter 500, 15 px, −0.01em tracking) on
`radius.sm` (10 px) — rounded, never pill — min height 44 px
(`layout.touch-min`), 36 px compact in dense tools. Padding 12 / 20.
The 2 px `accent.ring` outline at 2 px offset appears on `:focus-visible`.

## Token mapping

| Variant | Background | Border | Label |
|:--|:--|:--|:--|
| Primary | `accent.fill` | none | `text.inverse` — white on Harbor Blue is 4.56:1; in dark, the fill is Gull and the label Abyss at 6.51:1 |
| Secondary | `surface.primary` | 1 px `line.boundary` | `text.primary` |
| Tertiary | none | none | `text.accent` |
| Destructive | `feedback.alert.solid` | none | `text.inverse` |
| Disabled | variant colour | variant border | 45% opacity (`opacity.disabled`) |

## States

- **Hover**: primary → `accent.hover` (`harbor-blue-deep` light,
  `gull-lift` dark); secondary fills `interaction.hover`; tertiary gains an
  underline. `transition.button-color` (400 ms, ease-out).
- **Pressed**: → `accent.active` with a 1 px inward transform at
  `duration.fast`. No shadow animation.
- **Focus**: the ring. The boundary does not change colour on focus.
- **Loading**: label replaced by a spinner (`currentColor`), button keeps
  its width; `aria-busy="true"`.
- **Disabled**: 45% opacity, no pointer events. Never colour-only; the
  reason is given in nearby helper text.

## Rules

- One primary per view. A dialog's primary sits right (inline-end in RTL).
- Button copy is verb + object, ≤ 4 words, and says what happens:
  `Book a call`, `Start a project` — never `Submit`.
- Icon buttons are square, 44 × 44, with an `aria-label` and tooltip.

## Do / don't

| Do | Don't |
|:--|:--|
| One primary per view | Two primaries side by side |
| Radius 10 px | Pill buttons |
| 44 px default height | 32 px buttons in marketing |
| Disabled at 45% with an explanation | Greyed-out with no reason |
| Verb + object copy | `Submit`, `Click here` |
