# Motion — calm by design

Soft Harbor moves like water, not like a machine. Motion confirms a change
of state and then gets out of the way. Marketing may reveal; tools should
barely move. Tokens: `foundations/tokens.json` → `duration.*`, `easing.*`,
`transition.*`, `travel.*`.

## Principles

| # | Principle | Test |
|:--|:--|:--|
| M1 | Motion explains a change of place. A sheet rises from the bottom; a popover grows from its anchor; a route fades from the direction of travel. | Every enter has a stated origin; centred fades are for dialogs only. |
| M2 | Exit is faster than enter. | Every exit ≤ 50% of its enter; exits use `ease-in`. |
| M3 | Only cheap properties. | `transform`, `opacity`, `clip-path` — never layout, never `box-shadow` as the animated value. |
| M4 | Operational views do not decorate. | Dashboards and tools animate opacity and colour only — no reveals, no travel. |
| M5 | Interruptible. | A hover that ends mid-tween eases back from where it is; no animation traps. |
| M6 | Reduced motion leaves a complete page. | With `prefers-reduced-motion`, everything is present and readable; reveals render in their final state. |

## Durations

| Token | Value | Use |
|:--|:--|:--|
| `instant` | 80 ms | Knobs, checks, carets |
| `fast` | 150 ms | Hover colour and opacity; small exits |
| `base` | 250 ms | Toggles, menus, popovers, dialogs, toasts. Travel ≤ 64 px |
| `slow` | 400 ms | Button colour; header return |
| `page` | 600 ms | Route crossfade |
| `reveal` | 800 ms | In-view reveals. Marketing only |
| `stagger` | 60 ms | Sibling stagger, cap 8 items |
| `tooltip-delay` | 300 ms | Tooltip show delay |
| `toast-hold` | 5000 ms | Toast self-dismiss |

Distance rule: ≤ 8 px travel → `instant` / `fast`; ≤ 64 px → `base`; a
full route → `page`; a marketing reveal → `reveal`.

## Easings

| Token | Curve | Use |
|:--|:--|:--|
| `out` | `cubic-bezier(0.22, 1, 0.36, 1)` | The house curve. Enters, reveals, hover transforms. Soft, no overshoot, no bounce. |
| `in-out` | `cubic-bezier(0.65, 0, 0.35, 1)` | Things that open and later close: toggles, accordions. |
| `in` | `cubic-bezier(0.55, 0, 1, 0.45)` | Exits. |
| `linear` | `cubic-bezier(0, 0, 1, 1)` | Progress bars, marquee, scrubbed tweens only. |

## Component transitions

Named composites in `transition.*`; which component uses which:

| Transition | Tokens | Used by |
|:--|:--|:--|
| `hover-color` | fast + out | Hover colours |
| `button-color` | slow + out | Button colour |
| `press` | fast + out | Button transform on press |
| `toggle` | base + in-out | Toggles, accordions |
| `menu-open` | base + out | Menus, popovers opening |
| `menu-close` | fast + in | Menus, popovers closing |
| `dialog-in` | base + out | Dialogs, sheets opening |
| `dialog-out` | fast + in | Dialogs, sheets closing |
| `toast-in` | base + out | Toasts |
| `reveal` | reveal + out | Marketing in-view reveals (≤ 20 px travel) |
| `route` | page + out | Route crossfade |

## Reduced motion

`prefers-reduced-motion: reduce` or the in-app `Motion: Reduced` setting:

- Every duration becomes 1 ms, travel becomes 0.
- Loops render static; scroll effects do not mount.
- Video autoplay (muted only) pauses.
- The page must be complete and readable in this state — verified per
  screen, not assumed.
