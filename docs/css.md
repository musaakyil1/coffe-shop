# CSS Tokens & Utilities

## CSS Custom Properties (Variables)

Defined at the root level and used throughout the stylesheet:

- `--main-color`: Accent color (buttons, highlights)
- `--black-color`: Near-black used for panels and footer
- `--bg-color`: Page background color
- `--border`: Shared border style for cards and elements

Usage:

```css
.btn {
  background-color: var(--main-color);
}
```

## Utility Classes

- `.btn`: Standard button styling (hover scales up slightly)
- `.heading` and `.heading span`: Section title styles and accent color

## Layout & Components (Key Selectors)

- `header`, `.navbar`, `.logo img`, `.icons i`: Top navigation and brand area
- `.home`: Hero section with background image
- `.about .row`, `.image`, `.content`: Two-column about section
- `.menu .box-container` and `.box`: Menu grid and cards
- `.products .box-container` and `.product-box`: Product grid and cards
- `.reviews .box-container` and `.box`: Testimonials grid and cards
- `.contact-us .row`, `.map`, `form`, `.input-box`: Contact section layout
- `.blogs .box-container` and `.box`: Blog cards with hover image zoom
- `footer .share`, `.links`, `.copyright`: Footer layout and interactions

## Responsive Breakpoints

- `@media (max-width: 800px)`: Shows mobile nav, stacks sections, adjusts typography
- `@media (max-width: 600px)`: Decreases root font size and icon sizes

## Theming Example

Override the accent color globally:

```css
:root {
  --main-color: #b27a5c;
}
```

