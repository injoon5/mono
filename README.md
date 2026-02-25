# Mono

A minimal CSS framework built on neutral tones, clear hierarchy, and honest defaults. No build step. No dependencies. Just a stylesheet and some sensible decisions.

Inspired by the quiet confidence of [Vercel](https://vercel.com), the precision of [Linear](https://linear.app), and the indie spirit of [Cargo](https://cargo.site). Designed to feel considered without being fussy.

---

## what's in the box

```
mono/
├── mono.css    — the whole framework, one file
├── index.html  — component reference & live preview
├── llms.txt    — machine-readable docs for LLMs
└── README.md
```

**`mono.css`** is everything. Design tokens, reset, typography, layout utilities, and every component — all in one file you can drop into any project. No preprocessor needed.

**`index.html`** is a standalone demo page. Open it in a browser and you have a full component reference with a working dark mode toggle, interactive components, and live examples. Good for poking around before committing.

**`llms.txt`** is a machine-readable reference of every token, class, and HTML pattern. Paste it into any LLM context window and it can generate correct, idiomatic Mono code without hallucinating class names.

---

## usage

```html
<link rel="stylesheet" href="mono.css" />
```

That's it. No npm, no bundler, no config.

---

## what's included

**Foundations**
- Design tokens — spacing, radius, shadows, type scale, all as CSS custom properties
- Pretendard typeface — clean, Latin + Korean, reads beautifully at any size
- oklch color palette — 11 neutral steps, perceptually uniform
- Light + dark mode — automatic via `prefers-color-scheme`, manual via `data-theme="dark"`

**Layout**
- `.container` — centered, max-width, with size variants (sm / md / lg / xl)
- `.grid` — 2, 3, 4 column, and auto-fill
- `.stack` / `.cluster` — flex helpers for vertical and horizontal composition
- `.section` — consistent section padding with size variants

**Components**
- Nav — sticky, frosted glass, no dividers
- Buttons — primary / secondary / ghost, four sizes, group support
- Input / Textarea / Select — shared style, hover/focus/error/disabled states
- Checkbox / Radio / Switch / Range — all custom-styled with native HTML
- Card — header, body, footer slots; hover and inverted variants
- Accordion — native `<details>`/`<summary>`, no JavaScript
- Dropdown — native `<details>`/`<summary>`, no JavaScript
- Modal — native `<dialog>`, focus trapping and Escape key for free
- Loading — spinner, skeleton shimmer, animated dots
- Badge, Alert, Avatar, Table, Code, Divider

---

## responsive

Two breakpoints, desktop-first:

| Breakpoint | Width | Changes |
|---|---|---|
| Tablet | ≤768px | Nav links collapse to hamburger + slide-out drawer. Headings scale down. |
| Mobile | ≤640px | Nav actions hide. Grids go to 1 column. Headings scale down further. Modals become bottom sheets. |

Nothing to configure — it's all in the stylesheet.

---

## theming

All colors are CSS custom properties. Override in your own stylesheet:

```css
:root {
  --color-accent: oklch(0.55 0.18 250); /* swap in any accent color */
}
```

Dark mode is handled for you. System preference is respected automatically. To override manually, set `data-theme="dark"` or `data-theme="light"` on `<html>`.

---

## design notes

The type scale uses [Pretendard](https://github.com/orioncactus/pretendard), served from jsDelivr. Letter-spacing is tightened progressively for larger sizes and eased out for body copy — the kind of detail that makes text feel intentional.

Colors are written in `oklch` for perceptual uniformity. The whole palette is achromatic (zero chroma) which means it pairs cleanly with any accent color you want to introduce.

Radius is intentional — small but present. Enough to feel modern, not so much it feels bubbly.

Interactive components (accordion, dropdown, modal) use native HTML elements — `<details>`, `<summary>`, `<dialog>` — so they work without any JavaScript and get browser-native accessibility behaviours for free.

---

## browser support

Modern browsers. Uses `oklch()`, CSS custom properties, `backdrop-filter`, native `<dialog>`, `@starting-style` for enter animations, and `color-mix()` for button states. No IE. No apologies.

---

## license

MIT. Use it, fork it, make it yours.