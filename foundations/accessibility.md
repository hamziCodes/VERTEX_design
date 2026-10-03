# Accessibility

WCAG 2.1 AA is a build-time requirement, not a wish list. Every ratio below
was measured against its actual surface. When a token changes, re-measure.

## Contrast targets

| Class | Requirement | Key measured pairs |
|:--|:--|:--|
| Body and UI text | ≥ 4.5:1 (AA) | ink 13.51:1, slate 4.84:1 (light); foam 14.72:1, spray 7.37:1 (dark) |
| Accent as text | ≥ 4.5:1 | `#3E5C6B` 6.57:1 (light); `#82A5B6` 6.51:1 (dark) |
| Text on fills (buttons, badges, tooltips) | ≥ 4.5:1 | white on Harbor Blue 4.56:1; abyss on Gull 6.51:1; white on success 4.96:1, on alert 4.90:1 |
| UI boundaries (fields, focus ring) | ≥ 3:1 | Fog Line 3.39:1, Tide Line 3.06:1, focus ring 4.20:1 light / 6.51:1 dark |
| Large text (≥ 24 px, or ≥ 19 px at 600) | ≥ 3:1 | slate-on-Warm-Sand 4.46:1 is body-borderline — large text only there |
| Decorative hairlines | no requirement | Driftwood 1.24:1, Reef 1.62:1 — never carry meaning alone |

### The accent contrast rule

Light accent `#5B7A8C` is **4.20:1 — not for body text**. It is a fill and
graphics colour. The text-grade accent is `#3E5C6B` (6.57:1); that is the
only blue a paragraph, link, or label may wear in light mode. Dark accent
`#82A5B6` is text-safe (6.51:1) and may be used for both fills and text.

Verify's solid `#4E7A8C` is 4.32:1 — solid badges and icons only, never
body text; verify text in light mode is `#3E5C6B`.

## Rules

1. Focus visible everywhere: 2 px `accent.ring`, 2 px offset,
   `:focus-visible`. Never `outline: none` without an equivalent ring. In
   forced-colours mode the ring maps to `Highlight`.
2. Touch targets ≥ 44 × 44 px (`layout.touch-min`); adjacent targets ≥ 8 px
   apart or visibly divided. Desktop-only controls ≥ 24 × 24.
3. Every control has an accessible name from a visible label (`<label for>`)
   or `aria-label`; placeholder is never the name.
4. Errors are announced (`role="alert"` on the summary) and focus moves to
   the first invalid field.
5. Overlays trap focus, move it to the title or first control, and return it
   to the opener on close. `Esc` closes the topmost overlay.
6. Keyboard-only path complete: Enter/Space activate; arrows within
   composite widgets (roving tabindex in tabs, menus, segmented controls);
   `Cmd/Ctrl+K` for command palettes where one exists. No keyboard traps,
   no positive `tabindex`.
7. 200% zoom without loss; 320 px wide without horizontal scroll (tables
   scroll inside their own wrapper or become card lists).
8. Forced colours (Windows HC): controls keep a real `line.boundary`
   border; lines map to `CanvasText`, the ring to `Highlight`; icons use
   `currentColor`.
9. Reduced motion leaves a complete page (see `foundations/motion.md`).
10. **No colour-only state.** Every state has a second channel: badges carry
    labels; invalid fields have messages and icons; selected rows have a 2 px
    border and a check; charts have legends and hover labels.
11. Live regions for async updates (`role="status"` toasts,
    `aria-live="polite"` on updating regions); charts ship an accessible
    table or text summary, never canvas alone.
12. Images: alt describes the content; decorative images get `alt=""`;
    icons are `aria-hidden` unless they are the only content.

## Content

Plain language, sentence case, ≤ 20-word UI sentences (see
`foundations/content-voice.md`). Urdu content carries `lang="ur"` so
screen readers switch voice.
