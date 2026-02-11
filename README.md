# CDS Tokens

> **Professional design tokens. 3-layer architecture. Free forever.**

Comprehensive color system, spacing, and typography. Use in any framework.

[![npm](https://img.shields.io/npm/v/cds-tokens.svg)](https://www.npmjs.com/package/cds-tokens)
[![MIT](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

---

## Install

```bash
npm install comprehensive-design-tokens
```

## Use

```js
import tokens from 'comprehensive-design-tokens';

// Access any token
tokens.core.color.indigo[500]; // "#6366f1"
tokens.alias.primary; // "indigo-500"
tokens.light.button.primary; // Uses alias
```

---

## Architecture

**3 layers. Industry standard.**

```
Core → Alias → Theme
```

### Core (Primitives)

Raw values only. Never changes per theme.

```json
{
  "color": {
    "indigo": { "500": "#6366f1" }
  },
  "spacing": { "4": "16px" }
}
```

### Alias (Semantic)

Meaningful names. References core.

```json
{
  "primary": "indigo-500",
  "success": "green-500"
}
```

### Theme (Context)

UI mapping. Light/dark modes.

```json
{
  "button": { "primary": "primary" },
  "background": { "default": "white" }
}
```

---

## Files

```
tokens/
├── core.json       # Colors, spacing, typography
├── alias.json      # Semantic layer (primary, success)
├── light.json      # Light theme
├── dark.json       # Dark theme
└── tokens.json     # Complete system (all combined)
```

---

## What's Inside

```
✓ 64 colors (8 palettes × 8 shades)
✓ 8 spacing values (4px → 64px)
✓ Typography scale
✓ Semantic aliases
✓ Light + Dark themes
```

---

## Quick Examples

### Tailwind

```js
// tailwind.config.js
const tokens = require('comprehensive-design-tokens');

module.exports = {
  theme: {
    extend: {
      colors: tokens.core.color,
    },
  },
};
```

### CSS Variables

```css
:root {
  --primary: #6366f1;
  --spacing-4: 16px;
}
```

### React

```js
import tokens from 'comprehensive-design-tokens';

const Button = styled.button`
  background: ${tokens.alias.primary};
  padding: ${tokens.core.spacing[4]};
`;
```

---

## Usage Rules

### DO

```js
// Use aliases for UI
button.color = tokens.alias.primary;

// Use themes for modes
background = tokens.light.background.default;
```

### DON'T

```js
// Skip layers
button.color = tokens.core.color.indigo[500];
```

---

## For Designers

**Update workflow:**

1. Edit `tokens/core.json` → Change base colors
2. Edit `tokens/alias.json` → Change meanings
3. Edit `tokens/light.json` → Update UI mapping

**Everything cascades automatically.**

for figma design system:figma.com/community/file/1599790277190309669/comprehensive-design-system

---

## For Developers

**Import what you need:**

```js
import core from 'cds-tokens/tokens/core.json';
import light from 'cds-tokens/tokens/light.json';
```

**Or use complete system:**

```js
import tokens from 'cds-tokens';
```

---

## Versioning

**Semantic versioning:**

- **MAJOR** → Breaking changes
- **MINOR** → New tokens
- **PATCH** → Value fixes

---

## License

MIT - Free for any project, commercial or personal.

---

## Contributing

Open an issue or PR. Simple as that.

---

**CDS Tokens** · Made with care. Shared with love.
