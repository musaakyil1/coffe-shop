## Styles

All styles are defined in `style.css` with CSS custom properties, utilities, and responsive rules.

### Theme Variables
Defined globally and used throughout the UI:

```css
:root {
  --main-color: #d3ad7f;
  --black-color: #13131a;
  --bg-color: #010103;
  --border: 0.1rem solid rgba(255, 255, 255, 0.3);
}
```

Usage:
```css
body {
  background-color: var(--bg-color);
  color: white;
}
.btn {
  background-color: var(--main-color);
}
```

### Utilities
- `.btn`: Button style with hover scale
- `.heading`: Section headings with accented `<span>`

### Layout
- Global section padding using `section { padding: 2rem 7%; }`
- Grid layouts via `.menu .box-container`, `.products .box-container`, `.reviews .box-container`, `.blogs .box-container`

### Component Highlights
- `.navbar a:hover`: Accent underline and color change
- `.menu .box:hover`: Invert colors on hover
- `.blogs .box:hover .image img`: Scale on hover

### Responsive
- At `max-width: 800px`:
  - `header .icons` become visible
  - `.navbar` becomes a dropdown panel and uses the `active` class to toggle
  - Section paddings reduce; hero text size scales down
- At `max-width: 600px`:
  - Base font size reduces for compact layouts

### Adding New Styles
Extend components by composing existing classes and leveraging the theme variables. Prefer adding modifiers (e.g., extra classes) rather than inlining styles.

