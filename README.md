# Mono

A minimal CSS framework built on neutral tones, clear hierarchy, and honest defaults. No build step. No dependencies. Just a stylesheet and some sensible decisions.

Inspired by the quiet confidence of [Vercel](https://vercel.com), the precision of [Linear](https://linear.app), and the indie spirit of [Cargo](https://cargo.site). Designed to feel considered without being fussy.

---

## what's in the box

```
mono/
├── README.md  — some nice things to know about
├── mono.css   — the whole framework, one file
├── llms.txt   — docs for llms
└── index.html — component reference & live preview
```

**`mono.css`** is everything. Design tokens, reset, typography, layout utilities, and every component — all in one file you can drop into any project. Around 600 lines. No preprocessor needed.

**`index.html`** is a standalone demo page. Open it in a browser and you have a full component reference with a working dark mode toggle, interactive accordion, dropdowns, modals, and skeletons. Good for poking around before committing.

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
- Accordion — animated open/close
- Dropdown — scale + fade, dividers, labels, danger items
- Modal — backdrop blur, scale-in, closes on Escape or backdrop click
- Loading — spinner, skeleton shimmer, animated dots
- Badge, Alert, Avatar, Table, Code, Divider

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

---

## browser support

Modern browsers. Uses `oklch()`, CSS custom properties, `backdrop-filter`, and `:has()` in a few places. No IE. No apologies.

---

## license

MIT. Use it, fork it, make it yours.