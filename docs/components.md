# Components

The site is organized into semantic sections. Use the class names and structure below to add, remove, or customize components.

## Header

- Container: `header`
- Key elements: `.logo img`, `.navbar`, `.icons i`, `#menu-btn`
- Purpose: Top navigation with brand and action icons; mobile menu toggle lives here.

Customization tips:
- Replace `images/logo.jpg` to change the logo.
- Add or remove links inside `.navbar`.
- Font Awesome icons require the CDN in `index.html` `<head>`.

## Home (Hero)

- Container: `.home`
- Content: `.content > h3`, `p`, `.btn`
- Purpose: Hero message with background image.
- Customize the background image via `.home { background-image: url("./images/home.jpg") }` in `style.css`.

## About

- Container: `.about`
- Layout: `.row` with `.image` and `.content`
- Purpose: Two-column section with an image and description.

## Menu

- Container: `.menu`
- Grid: `.box-container`
- Card: `.box` with `img`, `h3`, `.price`, `.btn`
- Purpose: Showcase menu items.

To add a menu card:
```html
<div class="box">
  <img src="images/menu-1.jpg" alt="menu">
  <h3>tasty and healthy</h3>
  <div class="price">$14.99 <span>$19.99</span></div>
  <div class="btn">Buy Now</div>
  </div>
```

## Products

- Container: `.products`
- Grid: `.box-container`
- Card: `.product-box` with `.image img`, `.content h3`, `.stars`, `.price`

## Reviews

- Container: `.reviews`
- Grid: `.box-container`
- Card: `.box` with `p`, `img`, `h3`, `.stars`

## Contact Us

- Container: `.contact-us`
- Layout: `.row` with `iframe.map` and `form`
- Form elements: `.input-box > span + input`, `.btn-container .btn`

## Blogs

- Container: `.blogs`
- Grid: `.box-container`
- Card: `.box` with `.image img` and `.content` (`.title`, `span`, `p`, `.btn`)

## Footer

- Container: `footer`
- Elements: `.share i` (social icons), `.links a` (footer nav), `.copyright`

## Navigation & Anchors

- Sections can be linked by adding matching `id` attributes to sections and `href="#section-id"` on nav links.
- Example: `<section class="contact-us" id="contact-us">` pairs with `<a href="#contact-us">Contact</a>`.

