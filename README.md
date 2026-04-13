# Apple Design System

A lightweight, framework-agnostic implementation of Apple's Human Interface
Guidelines as reusable design tokens and CSS primitives.

> Inspired by Apple HIG · SF Pro type ramp · iOS/macOS system colors
> · 4pt spacing grid · Light + dark mode

## What's inside

| File | Purpose |
|------|---------|
| `apple-design-system.css` | Full stylesheet: tokens + components |
| `design-tokens.json` | Raw tokens (colors, spacing, typography) — consumable by Style Dictionary, Figma Tokens, Tailwind, etc. |
| `index.html` | Interactive demo / component playground |
| `tokens.scss` | SCSS variables mirroring the CSS custom properties |

## Quick start

Drop the CSS into any HTML page:

```html
<link rel="stylesheet" href="apple-design-system.css">

<div class="apple-container">
  <header class="apple-header">
    <h1>Hello, Apple</h1>
    <p>A beautifully simple UI.</p>
  </header>

  <div class="apple-card">
    <div class="apple-form-row">
      <label>Mode</label>
      <div class="apple-input-wrap">
        <label class="apple-toggle">
          <input type="checkbox" checked>
          <span class="apple-toggle-slider"></span>
        </label>
      </div>
    </div>
  </div>

  <button class="apple-btn apple-btn-primary apple-btn-block">Continue</button>
</div>
```

## Design tokens

### Color

System palette exposed as CSS custom properties and JSON:

```
--apple-blue     #0071e3    --apple-green    #34c759
--apple-indigo   #5856d6    --apple-red      #ff3b30
--apple-purple   #af52de    --apple-orange   #ff9500
--apple-pink     #ff2d55    --apple-yellow   #ffcc00
```

Semantic aliases (`--accent`, `--bg-primary`, `--text-primary`, …) adapt
automatically to `prefers-color-scheme: dark`.

### Typography — SF Pro type ramp

| Role         | Size |
|--------------|------|
| Large Title  | 34px |
| Title 1      | 28px |
| Title 2      | 22px |
| Title 3      | 20px |
| Headline     | 17px (semibold) |
| Body         | 17px |
| Callout      | 16px |
| Subhead      | 15px |
| Footnote     | 13px |
| Caption 1    | 12px |
| Caption 2    | 11px |

All utilities are prefixed `.apple-` (e.g. `.apple-title-1`, `.apple-body`,
`.apple-footnote`).

### Spacing — 4pt grid

`--space-1` … `--space-10` map to `4px` … `64px`.

### Radius

`--radius-xs` `4`, `--radius-sm` `8`, `--radius-md` `12`, `--radius-lg` `16`,
`--radius-xl` `20`, `--radius-2xl` `28`, `--radius-full` `9999`.

## Components

- **Card** — `.apple-card`, `.apple-card-elevated`, `.apple-card-flat`
- **Form row** — `.apple-form-row` + `.apple-input` / `.apple-select`
- **Toggle** — `.apple-toggle` (iOS-style 51×31px)
- **Buttons** — `.apple-btn` + `.apple-btn-primary|secondary|success|danger|ghost`
  with `.apple-btn-block`, `.apple-btn-sm`, `.apple-btn-lg`
- **Progress** — `.apple-progress` + `.apple-progress-fill`
- **Dropzone** — `.apple-dropzone` (hover + `.is-active` states)
- **Badges** — `.apple-badge-neutral|accent|success|warning|danger`

## Dark mode

Dark mode is automatic via `prefers-color-scheme`. To force a mode, add
`class="apple-light"` or `class="apple-dark"` to an ancestor element.

## Accessibility

- Respects `prefers-reduced-motion` (animations collapse to 0.01ms)
- Semantic color contrast meets WCAG AA on both light and dark backgrounds
- Focus rings use a 3px `rgba(0, 113, 227, 0.2)` halo matching macOS

## License

MIT — you may use, modify, and redistribute freely. "Apple", "iOS", "macOS",
and "SF Pro" are trademarks of Apple Inc. This project is an independent
community implementation inspired by Apple's public HIG and is not affiliated
with or endorsed by Apple.
