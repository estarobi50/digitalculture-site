# Digital Culture Web Designs: design system

Applies to `portfolio.html` (digitalcultureit.com/portfolio.html). Direction taken from the existing page and brand, not from outside reference sites (UXKIN was not connected).

**Feeling:** cinematic, technical, quiet. A dark screening room where the client work is the light source.

## Color (dark only)

| Token | Value | Role |
|---|---|---|
| `--ink` | `#07090d` | Page background |
| `--night` | `#0d1219` | Card and image fallback background |
| `--bone` | `#ece7dc` | Primary text, solid buttons |
| `--dim` | `#a3acb7` | Secondary text (7.9:1 on ink) |
| `--faint` | `#8b94a0` | Footer and fine print (6.3:1) |
| `--line` | `rgba(236,231,220,.14)` | Borders, chips |
| `--cyan` | `#19e3ff` | Brand accent: the italic word in the H1, hero canvas. Nothing else. |
| `--tungsten` | `#f2c98a` | Warm accent: focus ring, section kicker, Vesper hover |
| `--lagoon` | `#7fd6d2` | Cool accent: hero eyebrow, dental hover |

Each project card has its own hover tone (`--tone`): tungsten for Vesper, lagoon for both dental sites, soft blue `#8fb4e8` for Anchorage. Text contrast is at least 4.5:1 everywhere, large text 3:1.

## Typography

- **Display:** Instrument Serif, 400. H1 `clamp(3rem, 8.6vw, 8.4rem)`, H2 `clamp(2.4rem, 5vw, 4.4rem)`, card titles `clamp(2rem, 5.2vw, 5rem)`. Line height 0.95 to 1.05.
- **Body and UI:** Manrope 300 to 600. Body 16px at 1.6; hero lede and card copy at weight 300; buttons and chips 500 to 600.
- **Eyebrows and kickers:** Manrope 500, 0.8rem, uppercase, 0.28 to 0.32em tracking.
- Copy lines are capped at 46 to 52ch.

## Spacing

Scale: `--s-1` 8px, `--s-2` 16, `--s-3` 24, `--s-4` 40, `--s-5` 64. Page gutter `--gutter: clamp(20px, 4vw, 56px)`. Content width 1500px. Gap between project scenes `clamp(70px, 10vw, 140px)`.

## Shape and depth

Radius: `--r-sm` 4px (thumbnails), `--r-md` 6px (project frames), `--r-pill` 999px (buttons, chips). One shadow, `--shadow-lift`, on project frames. Film grain and vignette sit over the whole page.

## Page structure (v3)

Hero, four project cases with live scaled previews in a browser frame (alternating sides, one accent tone each), a four-step process, "Built by the people who run your IT", and a contact close (phone, message, email). No testimonials, client counts or prices: none are on file, so none are shown.

## Components

- **Primary button (`.open`):** bone fill, ink text, pill. Hover takes the project tone and widens the gap to the arrow.
- **Ghost button (`.cta`):** 1px bone border, transparent. Hover inverts to bone fill.
- **Project scene:** 2.39:1 frame (4:3 on mobile), image with scroll parallax, title and button on a bottom gradient, description plus chips below, three-thumbnail strip.
- **Chips (`.meta li`):** 1px `--line` border, pill, `--dim` text.
- **Focus:** keyboard focus rings the whole project frame in tungsten; other controls get a 2px tungsten outline. A "Skip to projects" link appears on first Tab.
- **Nav:** fixed, gains a blurred backing after the hero. Wordmark is "Digital Culture Web Designs" (shortened on phones). "Main site" always visible; "Start a project" pill on larger screens.
- **Live preview:** the real site in an iframe, scaled from 1440px (900px on phones), loaded when near the viewport, over the project's still image. A link overlay opens the site in a new tab.

## Motion

Letterbox bars open on load, H1 tracks in from a blur, then eyebrow, lede and button fade up in sequence. Hero canvas (hex grid, network, traces) is live. Project stills tilt in 3D, light follows the cursor. `prefers-reduced-motion` turns all of it off.

## Imagery

Each project is shown with its own site's hero plus three supporting stills. No stock art, no icon set beyond the single arrow glyph. Project descriptions say what the site does, not how it feels.

## Rules

1. Cyan is for brand glow (hero animation, contact close, button hover). No accent-colored words in headlines.
2. New projects copy an existing `.scene` block and add one `--tone`.
3. Use tokens, not raw values, for new CSS.
4. Keep "Project listings, prices and addresses are sample content." in the footer while the sites use demo data.
