## Project Structure

### Top-level files
- `index.html`
- `style.css`
- `main.js`
- `images/` (asset folder)

### HTML Layout Overview
The page is organized into semantic sections. Each section uses BEM-like class names and utility classes.

```html
<header>
  <a class="logo"><img /></a>
  <nav class="navbar"> ... </nav>
  <div class="icons">
    <i id="menu-btn" class="fa-solid fa-bars"></i>
  </div>
  <!-- Mobile state toggles .navbar.active -->
</header>

<section class="home"> ... </section>
<section class="about"> ... </section>
<section class="menu"> ... </section>
<section class="products"> ... </section>
<section class="reviews"> ... </section>
<section class="contact-us" id="contact-us"> ... </section>
<section class="blogs" id="blogs"> ... </section>

<footer> ... </footer>
```

### Key Elements
- `header .logo`: Site logo
- `header .navbar`: Primary navigation; gains `active` on mobile toggle
- `header .icons`: Search, cart, and menu icons
- `.home .content`: Hero title, description, and CTA button
- `.about .row`: Split image/content layout
- `.menu .box-container .box`: Repeated menu item cards
- `.products .box-container .product-box`: Product cards with rating and price
- `.reviews .box-container .box`: Customer review cards
- `.contact-us .row form`: Contact form with inputs and submit button
- `.blogs .box-container .box`: Blog cards with image and text
- `footer .share`, `footer .links`, `footer .copyright`

