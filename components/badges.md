# Badges and statuses

## Anatomy

A badge is the `badge` type (Plex Mono 400, 11 px, uppercase, +0.1em
tracking) on `radius.pill`, with 6 / 12 padding. A status always pairs
icon + label — never a dot alone, never colour alone.

## Token mapping

| Variant | Background | Border | Text | Icon |
|:--|:--|:--|:--|
| Neutral / info | `accent.soft` | harbor-blue 38% | `feedback.info.text` (`#3E5C6B` / Gull) | 16 px line icon |
| Success | `feedback.success.bg` | sea-glass 38% | `feedback.success.text` | check |
| Alert | `feedback.alert.bg` | buoy 38% | `feedback.alert.text` | alert icon |
| Verify | `feedback.verify.bg` | lantern 38% | `feedback.verify.text` | seal / check-circle |
| Solid (counts, new) | `accent.fill` | none | `text.inverse` | none |

Text always uses the text-grade colour (≥ 4.5:1 on its tinted bg):
`#3E7C6B`-grade for verify in light is `#3E5C6B`; verify's solid
`#4E7A8C` is 4.32:1 and is never body text. In dark mode, `-bright`
variants carry the text.

## States

Badges are static. Count badges update via `aria-live="polite"`; a
changing status announces itself (`role="status"`). Dismissible badges
(rare) get a 24 px icon button with an `aria-label`.

## Rules

- One or two words: `New`, `In progress`, `Live`. Never a sentence.
- Status in a list row pairs the badge with a 2 px selected border when
  the row is selected.
- Mono uppercase is a style; the string is written in sentence case.

## Do / don't

| Do | Don't |
|:--|:--|
| Icon + label, always | A coloured dot alone |
| Tinted bg with matching border at 38–40% | Solid alert fill with white text for a soft status |
| Pill radius | Square badges |
| Text-grade colours (≥ 4.5:1) | `#4E7A8C` as badge text |
