## Styles, Variables, and Utilities

### CSS Custom Properties

Defined in `:root` (typo in file is `::root`):

- `--main-color`: Accent color used for buttons and highlights.
- `--black-color`: Dark background blocks.
- `--bg-color`: Page background.
- `--border`: Standard subtle border used across components.

Usage example:

```css
.btn { background-color: var(--main-color); }
```

### Global Resets and Base

- Universal reset for margins, padding, box model, and `text-transform: capitalize`.
- `html { font-size: 10px; scroll-behavior: smooth; }` for easy `rem` sizing.
- Custom scrollbar styles for WebKit.

### Reusable Classes

- `.btn`: Primary button style with hover scale.
- `.heading` and `.heading span`: Section headers with accent span.
- `.box-container`: CSS Grid used in multiple sections with responsive columns.

### Section-specific Blocks

- `.home`: Full-bleed hero with background image.
- `.about .row`: Two-column layout.
- `.menu .box`, `.products .product-box`, `.reviews .box`, `.blogs .box`: Card-like containers with borders and hover effects.

### Responsive Behavior

Two breakpoints:

- `@media (max-width: 800px)`
  - Header navbar becomes a floating dropdown hidden by default.
  - `.navbar.active` displays the menu as a column.
  - Section padding reduced, hero text resized.

- `@media (max-width: 600px)`
  - Base font-size reduced to `8px`.
  - Icon sizes decreased.

### Notes and Best Practices

- If you rename `.navbar` or `#menu-btn`, update both the CSS responsive rule and `main.js` selectors.
- Prefer `rem` units for scalable typography.
- Keep image dimensions reasonable to maintain performance.
