# Button

A pill-shaped call to action with a 2px ink border and a hard offset shadow that grows on hover.

Static rendition of `.btn` from `site/src/styles/global.css`; the site has no React component for it. Markup: `<a class="btn btn-ink">Label →</a>` (or a `<button>`). The consumer supplies the label, the href and one variant class.

| Variant | Fill / text | Shadow | Use |
| --- | --- | --- | --- |
| `btn-ink` | `ink` / white | 5px `red` | The primary action in a group ("See pricing →"). |
| `btn-light` | white / `ink` | 5px `yellow` | The secondary action beside btn-ink ("Schedule a call"). |
| `btn-yellow` | `yellow` / `ink` | 5px `ink` | A loud single action on cream or ink grounds. |
| `btn-red` | `red` / white | 5px `ink` | Use sparingly: white on `red` is 3.1:1, which fails AA at the 15px label size. Prefer ink text on red, or keep it to 19px+ bold. |

Hover moves the button up-left 2px and the shadow to 7px. Under `prefers-reduced-motion` transitions are cut to 0.01ms. Focus uses the global 3px ink outline at 3px offset.
