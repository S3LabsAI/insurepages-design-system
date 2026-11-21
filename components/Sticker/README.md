# Sticker

A small white pill with an ink border and a 3px hard shadow, used for nav calls to action, badges and short tags.

Static rendition of `.sticker` from `site/src/styles/global.css`. Markup: `<a class="sticker">Start now</a>` or a `<span>`. The consumer supplies the text and, optionally, a background token: the header marks the current page with a `lavender` sticker, the hero uses `yellow` and `green` rectangles (radius-tag / radius-eyebrow) rotated ±2deg. Fill colours other than white take ink text only. Hover lifts it 1px and the shadow to 4px.
