## Components and Markup

This site is organized into semantic sections. Use these as building blocks.

### Header

Includes logo, primary navigation, and action icons.

Key elements:

- `.logo` image
- `.navbar` with anchor links
- `.icons` containing search, cart, and the mobile menu button `#menu-btn`

Responsive behavior: On small screens, the navbar is hidden until the menu button toggles `.navbar.active`.

### Home Section `.home`

- Full viewport hero with background image, heading, paragraph, and primary button `.btn`.

### About Section `.about`

- `.row` with `.image` and `.content` columns.

### Menu Section `.menu`

- `.box-container` grid of `.box` cards.
- Each `.box` includes an image, title, `.price` (with optional discounted `<span>`), and `.btn`.

### Products Section `.products`

- `.box-container` grid of `.product-box` cards with `.image` and `.content` including `.stars` and `.price`.

### Reviews Section `.reviews`

- `.box-container` of testimonial `.box` items with avatar, text, name, and `.stars`.

### Contact Section `.contact-us`

- `.row` with `iframe.map` and `form`.
- The form uses `.input-box` wrappers with an icon `<span>` and `<input>`.

### Blogs Section `.blogs`

- `.box-container` of blog `.box` cards containing `.image` and `.content` with `.title` and teaser.

### Footer

- `.share` social icons, `.links` repeated nav, and `.copyright`.

## Example: Adding a New Menu Item

```html
<div class="menu">
  <div class="box-container">
    <div class="box">
      <img src="images/menu-new.jpg" alt="menu" />
      <h3>signature latte</h3>
      <div class="price">$9.99 <span>$12.99</span></div>
      <div class="btn">Buy Now</div>
    </div>
  </div>
  <!-- existing boxes ... -->
  
</div>
```

## Accessibility Tips

- Provide descriptive `alt` attributes for all images.
- Ensure anchor text is meaningful.
- Consider focus styles for interactive elements.
