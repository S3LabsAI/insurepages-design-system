# InsurePages

The design system behind InsurePages by S3 Labs: websites for independent insurance agents, live in days, accessible by default. Synced from `S3LabsAI/insure-pages` at `main@b4ed521` (the Astro marketing site in `site/`).

The look is neo-brutalist "sticker": chunky rounded shapes, 2px ink borders, hard offset shadows with no blur, a few slight rotations, all on a warm cream ground. It should feel friendly, fast and a little loud, never corporate.

## Content fundamentals

- Speak to the agent directly, in plain words and short sentences: "If they can't find you, they'll find another agent."
- Lead with concrete numbers: "starting at $499", "goes live in a couple weeks", "Starter $499 one-time · Silver $599 + $25/mo · Gold $699 + $75/mo".
- Promise ownership and simplicity: "You own the site and the domain." "No long-term contracts."
- Accessibility is a selling point, but never promise legal immunity or advertise a conformance level. The product reduces risk; it does not guarantee against suits.
- US phone numbers only, in `(XXX) XXX-XXXX` shape; use `(XXX) 555-01XX` for fictional ones.
- Button labels are verbs with an arrow when they move you on: "See pricing →", "Begin →". "Schedule a call" has no arrow.

## Visual foundations

**Colour.** `cream` is the page; `cream-deep` alternates bands; `ink` does text, borders, shadows and the footer ground. Five flat brand hues (`red`, `yellow`, `green`, `blue`, `lavender`) fill stickers, cards and numbered steps, usually in that order (method steps 1–5). Every hue takes `ink` text. White text goes only on `ink`, or on `red` at 24px+ (19px bold), because white on red is 3.1:1. On the ink footer use `yellow` and `link-on-ink` for text accents. Supporting paragraphs use `body-secondary`; captions use `muted`.

**Type.** Two self-hosted variable faces. Unbounded (`display`, weight 700, tight tracking -0.02 to -0.04em, leading 1–1.15) for headlines, prices and step numbers. Plus Jakarta Sans (`sans`) for everything else: body at 16px/1.55, ledes at 18–20px weight 500, labels at 14–15px weight 600–700, eyebrows at 12px uppercase with 0.08em tracking. Display sizes are fluid in code (`clamp()`); the type styles record the desktop maximum.

**Shape and depth.** Pills (`radius-pill`) for buttons and stickers; `radius-card` 24px for cards; `radius-tag` 8px for labels. Depth is only ever a hard offset shadow (`shadow-sticker` 3px up to `shadow-card-hover` 9px). Buttons swap the shadow colour for contrast: `btn-ink` casts `red`, `btn-light` casts `yellow`. Hover lifts the element up-left and grows the shadow; nothing blurs, nothing glows, no gradients.

**Rotation.** Hero stickers and the hero highlight tilt ±2deg. Keep it to one or two elements per view.

**Layout.** Container max 1280px with 40px side padding; sections breathe at 120px vertical (72px on mobile); section headers are centred with 64px below. Most layouts collapse to one column under 900px.

**Accessibility.** WCAG 2.1 AA is a product invariant. Focus is a 3px `ink` outline at 3px offset with `radius-focus`. A skip link sits first in the page. `prefers-reduced-motion` cuts transitions and smooth scroll.

## Iconography

The site uses Unicode marks inline (✦, ★, →) and small inline SVGs at 32px in pillar cards; there is no icon set in the repository. See the Logos group for the lockup and favicon.

## Components

Button, Sticker and SectionHeader are static renditions of the CSS primitives in `global.css`, styled by `components/bundle.css` (copied verbatim). The site's section components are Astro, not a React library, so there is no live bundle.

## Not synced

- Section components (Header, Hero, TrustStrip, Pillars, Method, Pricing, ContactCta, Footer, and the templates/tools/resources sections, `site/src/components/**/*.astro`): not built, by choice. Route: read-only, static previews of the primitives only.
- Spacing, radius and shadow tokens are promoted from recurring literal values; the code defines only the nine colour variables. `body-secondary` (#3a3a3a), `link-on-ink` (#8fc7ff) and `white` are literals too.
- Fluid `clamp()` font sizes are recorded at their maximum; `tier` line height is assumed (1.2).
- The six template demos under `site/public/demos/` use their own fonts and palettes and are not part of this system.
- Single light theme: the site has no dark mode.
