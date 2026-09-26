# New website

Build a marketing or product site as if every scroll-stop were an Apple still.

Map the article, do not invent a generic SaaS landing. Read `references/principles.md` for the video→web table.

Identity first: the hero is a way to belong by choosing the product, not a 12-feature dump.

## Information architecture

Write sections like shots:

| # | Section | One idea | Hero | Field | Type on screen | Motion |
|---|---|---|---|---|---|---|
| 1 | Hero | Belonging + product | product or wordmark | void | 1 headline, 1 line support, 1 CTA | ease in, long hold |
| 2 | Proof | One capability | UI or object | same void family | short label + one sentence | stagger, then rest |
| … | | | | | | |
| n | Close | Mark + next step | logo | void | wordmark + one CTA | settle, no spin |

- 5–8 sections max on a homepage
- Product or promise visible without scrolling on desktop
- One primary CTA per view. Secondary is text, not a second filled button
- No logo soup, no 12-feature grids in the first screen

## Constitution (`theme`)

Lock before components:

- 3 colors — field, ink, accent (accent lives on product/CTA, not on the field)
- 2 typefaces or one family with 2 weights
- Display tracking +0.02 to +0.04em
- Body 18–21px, line-length 45–70ch
- Radius small and consistent, or none
- Space scale that produces real emptiness (section padding 96–160px desktop)
- Motion tokens — duration, easing, one spring

Pages may not invent tokens.

## Layout

- Centered or single-axis compositions
- Quiet field + loud product
- Generous gaps. If a block feels busy, split into two sections
- Images of the product on void, not on textured stock
- UI screens in a simple device or naked — no fake 3D desks unless the brief is 3D
- Dark-on-dark and white-on-white fail contrast — fix stills first

## Copy

- Short. Specific. No slogan salad
- Headline is the idea of the section, not a keyword list
- Buttons name the action (`Get the wallet`, not `Learn more` twice)
- Do not invent testimonials, user counts, or press logos

## Stack

Prefer the repo's existing stack. If greenfield and unspecified:

- Semantic HTML, CSS tokens (or Tailwind with a locked theme), minimal JS
- Next/Astro/static is fine. Do not drag in three animation libraries
- Motion via CSS easing or one library (Motion/Framer) using the token curve
- Respect `prefers-reduced-motion`

## Motion on the web

- Scroll-triggered reveals are opacity + 12–24px rise, not flying cards
- Hover is a whisper (200–300ms). No bounce
- Adaptive rhythm — hero slower, proof can lift, close holds. Do not clone the same fade on every section
- Page-to-page should belong (shared color, axis, or object). Instant hard swaps feel like cheap cuts
- Page load — hero first, then one supporting move
- Video embeds inherit the video skill rules
- Sticky nav is thin, quiet, does not fight the hero
- Type system covers nav, headlines, UI chrome, and footnotes. No third family in the footer
- After a motion pass, delete hover/scroll noise that does not help understanding or engagement

## Ship checklist

- Tokens live in one file
- Homepage stills look like posters at 1440 and 390
- Type readable, contrast AA or better for body
- One idea per section survives a squint test
- No orphan fourth color in hover states
- Lighthouse performance not sacrificed for decoration
