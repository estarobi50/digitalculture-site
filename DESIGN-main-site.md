# Digital Culture IT Solutions: main-site design system

Applies to `index-aws.html` (the restyled home page; the live `index.html` is untouched). Direction taken from the existing brand, the VMware and AWS marketing sites as the user pointed to them, and the user's own feedback, not from the UXKIN library (it was not connected, so nothing here is based on real-site comparisons beyond those two references). Colors from the VMware references are published brand values, not read from the live site.

**Feeling:** calm, exact, enterprise. A well-lit operations room: soft grey-blue surfaces, deep navy for weight, one blue for action, a small green for proof.

## Color

| Token | Value | Role |
|---|---|---|
| `--canvas` | `#e2e8ed` | Page background (deliberately not white; reduces glare) |
| `--section` | `#d0d8df` | Alternating bands: process, pricing, FAQ |
| `--card` | `#f1f4f7` | Cards, header, inputs |
| `--tint` | `#d3e5ef` | Icon tiles, tags |
| `--ink` | `#14232c` | Headings (13.0:1 on canvas) |
| `--ink-body` | `#22323b` | Body text (10.7:1) |
| `--muted` | `#52555a` | Secondary text (6.1:1 on canvas, 5.2:1 on section) |
| `--line` | `#b8c3cc` | Hairlines and card borders |
| `--navy` / `--navy-deep` | `#0d3548` / `#08222f` | Hero overlay, stats band, founder band, featured price card, footer |
| `--blue` | `#007cb8` | Buttons and icons; white text on it is 4.6:1 |
| `--blue-hover` | `#00608f` | Button hover |
| `--blue-text` | `#00608f` | Blue text and links on light surfaces (4.8:1 or better) |
| `--brand-blue` | `#0091da` | Decorative only: gradient bars, icon strokes on dark |
| `--vm-green` | `#6db33f` | Decorative and large text on navy (5.0:1) |
| `--green-text` | `#36641c` | Small green text on light surfaces (4.9:1 or better) |
| `--vm-green-dark` | `#4d8a2a` | Checkmarks and non-text accents (3:1 is enough) |

Rules: one primary action color (blue). Green marks proof and progress, never actions. Small text never uses `--blue`, `--brand-blue`, `--vm-green` or `--vm-green-dark` on a light surface; it uses the `-text` twins. Reviews keep Google's own gold (`#fbbc04`) and logo colors.

## Typography

- **Family:** IBM Plex Sans for everything (stand-in for Amazon Ember), weights 400, 500, 600. Headings are sentence case at weight 500, never uppercase.
- **Scale:** section title `clamp(1.9rem, 3.4vw, 2.7rem)`; card title 1.05 to 1.3rem; body 0.9 to 1rem at 1.6 to 1.7; labels 0.75rem uppercase with 0.2 to 0.22em tracking.
- **Eyebrow:** 0.75rem, weight 600, `--green-text`, centered above each section title ("What we do", "How it works", "Why choose us", "Pricing", "Client reviews", "Answers").
- **Numerals:** tabular figures for prices, indexes and counters.

## Spacing and layout

8px base. Sections use 6rem vertical padding. Container up to 1320px; text blocks 640 to 760px. Card gaps 1.25 to 1.5rem. Index strips use 1px gaps over a `--line` background instead of separate borders.

## Shape and depth

Radius: 8px inputs and review cards, 10 to 14px tiles and fields, 16px feature cards, 20px large panels, 999px buttons and chips. Shadows: none at rest on light cards; one lift shadow on hover (`0 20px 40px -24px rgba(13,53,72,.4)`); a deeper one on the navy founder band, form panel and featured price card.

## Components

- **Primary button:** `--blue` fill, white text, pill, 0.04 to 0.06em tracking. Hover `--blue-hover`.
- **Outline button (on navy):** 1px white border, transparent; hover fills white.
- **Feature card:** gradient bar across the top (`--brand-blue` to `--vm-green`), navy icon tile, index number top right, hairline-separated checklist with green checks.
- **Index strip:** five cells in one bordered container, icon tile, title, one line of copy, index number.
- **Founder band:** navy panel with a faint grid and two soft glows, avatar ring, credential chips, numbered stack list.
- **Proof card:** tag, title, two lines, "Read the runbook" link; border turns blue and the card lifts 3px on hover and focus.
- **Review card:** Google style: initial avatar, name, source line, G badge, gold stars, plain text.
- **Assessment form:** two-panel card. Navy left panel (three steps, phone link), form right in two columns; labels uppercase 0.8rem; focus ring `0 0 0 4px rgba(0,124,184,.18)` with `--blue` border.
- **FAQ:** answers are hidden until the question or arrow is clicked; one open at a time.
- **Focus:** visible 3px blue ring on cards and links; inputs use the form ring above.

## Imagery and icons

One hero photo (`hero-datacenter-blue.jpg`) under a navy overlay. Line icons only, one stroke width, `--blue` on light tiles and `#7fd0f5` on navy tiles. No emoji, no gradient text, no glass effects.

## Motion

Reveal-on-scroll and the count-up stats stay from the original page. Hover transitions 0.2 to 0.3s on border, shadow and a 3px lift. All motion is disabled for `prefers-reduced-motion` on the proof cards; the original page's own reduced-motion handling covers the rest.

## Open decisions

- Whether to keep green as the proof accent or switch it to blue everywhere.
- The stats band shows animated counts; the final values come from the page script and should be confirmed before launch.
- Eyebrow labels are added in CSS, so they do not appear if styles fail to load; move them into the HTML if that matters.
