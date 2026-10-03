# Dividers

## Anatomy

A divider is 1 px `border.hairline` (Driftwood `#D8DFE4` / Reef `#2F414F`,
decorative 1.24:1 / 1.62:1). Horizontal rules span their container; vertical
dividers sit between inline items with 16 px of space on each side.

## Token mapping

| Part | Token |
|:--|:--|
| Line | `border.hairline` — 1 px solid, `line.hairline` |
| Spacing around | `space.4` (16) minimum |

## Where they appear

- Inside cards, between metadata rows.
- Between dense list rows.
- Under the nav bar.
- Nowhere else. Vertical rhythm prefers whitespace; a divider appears only
  when whitespace cannot do the job.

## Rules

- A divider is never the boundary of an interactive control. Fields,
  checkboxes, radios, and switches use `line.boundary` (Fog Line / Tide
  Line, ≥ 3:1).
- Hairlines never carry meaning alone — they separate visually, they do not
  encode state, selection, or validity.
- A divider is never gradient, double, or dashed in this system. One flat
  1 px line.

## Do / don't

| Do | Don't |
|:--|:--|
| Whitespace first, divider second | Dividers between every section |
| `line.hairline` for decoration | `line.boundary` as a decorative rule |
| 16 px of air around the line | Lines touching text |
