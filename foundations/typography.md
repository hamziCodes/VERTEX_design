# Typography

Three faces. Fraunces brings warmth to headlines; Inter does the quiet work
of reading; IBM Plex Mono labels and numbers. Tokens:
`foundations/tokens.json` → `font.*` (faces, weights, sizes) and
`typography.*` (composite roles). Products use the composite roles.

## The scale

| Role | Face / weight | Size | Line | Tracking |
|:--|:--|:--|:--|:--|
| Display L | Fraunces 600 | 40 → 96 px | 1.0 | −0.02em |
| Display M | Fraunces 600 | 32 → 72 px | 1.0 | −0.02em |
| Display S | Fraunces 600 | 24 → 36 px | 1.15 | −0.02em |
| H1 | Fraunces 600 | 30 → 36 px | 1.15 | −0.02em |
| H2 | Fraunces 600 | 24 px | 1.15 | −0.02em |
| H3 | Inter 600 | 20 px | 1.3 | 0 |
| H4 | Inter 600 | 17 px | 1.3 | 0 |
| H5 | Inter 500 | 15 px | 1.3 | 0 |
| H6 | Plex Mono 400, uppercase | 12 px | 1 | +0.1em |
| Body L (lead) | Inter 400 | 17 → 20 px | 1.5 | 0 |
| Body | Inter 400 | 15 → 17 px | 1.6 | 0 |
| Body S | Inter 400 | 13 px | 1.5 | 0 |
| Caption | Inter 400 | 12 px | 1.4 | 0 |
| Overline (kicker) | Plex Mono 400, uppercase | 12 px | 1 | +0.1em |
| Code | Plex Mono 400 | 14 px | 1.55 | 0 |
| Badge | Plex Mono 400, uppercase | 11 px | 1 | +0.1em |
| Numeric | Fraunces 700, tabular | 28 → 48 px | 1 | −0.02em |
| Button | Inter 500 | 15 px | 1 | −0.01em |

Fluid roles (`display-*`, `h1`, `body-l`, `body`, `numeric`) sit at their
minimum below `md`.

## Loading

- Fraunces: variable font, `wght` 400–700, optical sizing on.
- Inter: 400 / 500 / 600. IBM Plex Mono: 400 / 500.
- `font-display: swap` everywhere.
- Urdu: Noto Nastaliq Urdu for headings and body (`dir="rtl"`,
  `lang="ur"`, line-height 2.0, minimum 17 px), Noto Naskh Arabic for dense
  tables. Logical properties everywhere. Numerals stay Latin unless the
  product specifies otherwise.

## Usage rules

- **Sentence case everywhere** — headings, labels, buttons, nav, table
  headers. Uppercase is reserved for `overline`, `badge`, and `h6` (the
  string is written in sentence case; the case is a style).
- One display face per screen. Display L is for the hero; everything else
  steps down. Never two display roles competing.
- Headings `text-wrap: balance`; paragraphs `text-wrap: pretty`.
- Measure: body ≤ 68ch; a lead ≤ 25 words; a hero headline ≤ 3 lines.
- Numbers: `font-variant-numeric: tabular-nums` in columns, totals, timers,
  and counters. Stat numerals use the `numeric` role (Fraunces 700).
- Money: `Rs 12,500` (`Intl.NumberFormat("en-PK", { style: "currency",
  currency: "PKR", maximumFractionDigits: 0 })`); paisa on invoice lines
  only. Dates: `19 Sep 2026`; timestamps `19 Sep, 14:05`; schedules
  `Fri 19 Sep`. 24-hour in tools; 12-hour permitted in customer-facing
  surfaces.
- IDs, order numbers, codes: the `code` role (mono, not uppercase).
  Kickers and badges: mono uppercase.
- Emphasis in body copy is Inter 600 or `text.accent` — never italics as the
  only signal, never all-caps.
- No em-dashes in UI text; no semicolons in UI copy; periods and commas.
- No 700 weight in UI text; 700 is numerals and the wordmark only.
