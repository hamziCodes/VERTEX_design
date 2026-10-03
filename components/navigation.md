# Navigation

## Top bar

68 px (`layout.nav-h`), `surface.canvas` at 80% + 12 px backdrop blur
(`blur.nav`), hairline bottom border. Left: the Studio mark or wordmark.
Centre: links in the `nav` role (Inter 400, 15 px). Right: the primary CTA
(one) and the theme toggle. The active item is `text.primary` 500 with a
2 px `accent.fill` underline bar — never colour alone.

## Token mapping

| Part | Token |
|:--|:--|
| Bar | `surface.canvas` 80% + `blur.nav` |
| Divider | `border.hairline` |
| Link | `nav` type, `text.secondary` |
| Active link | `text.primary` 500 + 2 px `accent.fill` bar |
| Hover | `text.primary`, `transition.hover-color` |

## Mobile

The same bar, hamburger → bottom sheet: `radius.xl` top corners,
`shadow.overlay`, `transition.dialog-in`. Links stack, `body` size,
one primary CTA at the bottom.

## App sidebar (tools and dashboards)

264 px (`layout.sidebar-w`), `surface.canvas`, hairline on the inline-end
edge, padding 24 / 16. Groups with an `h6` kicker; items icon 18 + label
`button` type, height 40. Current item: `text.primary` 500 with a 2 px
`accent.fill` bar at the inline-start and `aria-current="page"`. Collapses
to the 64 px rail (`layout.sidebar-rail-w`) at `lg`; below `md` it becomes
a drawer opened from the top bar.

## Tabs

A row of `button`-type labels; selected is `text.primary` + a 2 px
`accent.fill` indicator, rest is `text.secondary`; hairline under the row.
`role="tablist"`, arrow keys move (roving tabindex), ≤ 6 tabs, overflow
scrolls horizontally. Counts in mono after the label.

## Breadcrumbs

`body-s`, `text.secondary`, `/` separators, current item `text.primary`
and not a link, ≤ 4 levels, collapse the middle beyond 4. Hidden on phones;
the back button carries the parent.

## Skip links

`Skip to main` first in the DOM.

## Do / don't

| Do | Don't |
|:--|:--|
| Active state = colour + bar | Active = colour alone |
| One primary CTA in the bar | A primary action competing with the page header |
| Same bar on mobile, hamburger → sheet | A different nav grammar per breakpoint |
| `aria-current="page"` on the current item | Guessing current from the URL in CSS only |
