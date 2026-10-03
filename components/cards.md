# Cards

## Anatomy

A card is `surface.primary` on `border.hairline`, `radius.md` (14 px),
padding 24, `shadow.rest` (flat — cards rest on borders, not shadows). A
card's media shares the card's radius; corners stay consistent. Card
headings are H3; metadata rows are `body-s` / `text.secondary` separated
by hairlines.

## Token mapping

| Part | Token |
|:--|:--|
| Background | `surface.primary` |
| Border | `border.hairline` |
| Radius | `radius.md` |
| Padding | 24 (`space.6`) |
| Shadow at rest | `shadow.rest` (none) |
| Hovered / draggable | `shadow.lift` over `duration.base` |
| Selected | 2 px `line.selected` border — never a colour wash alone |
| Heading | H3 |
| Metadata | `body-s`, `text.secondary`, hairline-separated rows |

## States

- **Rest**: flat, bordered. This is the default and the most common state.
- **Hover** (clickable cards only): `shadow.lift` + `duration.base` /
  ease-out. Non-clickable cards do not lift.
- **Selected**: the 2 px `line.selected` border plus a check — never
  colour alone.
- **Disabled / unavailable**: 45% opacity; the reason sits in caption text.

## Rules

- No card-in-card nesting beyond one level — use a section instead.
- A clickable card is a single `<a>` or button with the whole surface
  as the target; nested links inside a linked card need `position: relative`
  and careful focus order.
- Rhythm rule of three: padding 16 / internal gaps 16 / distance to the
  next card 32.

## Do / don't

| Do | Don't |
|:--|:--|
| Flat at rest, border-carried | Shadow as default decoration |
| One nesting level max | Card-in-card-in-card |
| Selected = 2 px border + check | Selected = tint only |
| Whitespace between cards | Card walls, bento mosaics |
