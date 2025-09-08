# Components & Structure

This site is a static HTML/CSS project enhanced with a small script. Below is the high-level structure and key classes/sections used by the UI.

## Layout overview

- Header (`<header>`)
  - Logo link (`a.logo > img`)
  - Navigation (`nav.navbar`)
  - Action icons (`div.icons`) including the hamburger `#menu-btn`
- Sections
  - `.home`: Hero headline and CTA button
  - `.about`: Image and content split layout
  - `.menu`: Grid of menu item boxes
  - `.products`: Grid of product boxes with ratings
  - `.reviews`: Customer testimonials
  - `.contact-us`: Map embed and contact form
  - `.blogs`: Blog teaser cards
- Footer
  - Social links, site links, and copyright

## Key interactive component: responsive navbar

- Trigger: `<i class="fa-solid fa-bars" id="menu-btn"></i>`
- Target: `<nav class="navbar"> ... </nav>`
- Behavior: `main.js` toggles the `active` class on `.navbar` when `#menu-btn` is clicked.

### Example markup

```html
<header>
	<a class="logo" href="#"><img src="images/logo.jpg" alt="logo" /></a>
	<nav class="navbar"> ... </nav>
	<div class="icons">
		<i class="fa-solid fa-bars" id="menu-btn"></i>
	</div>
</header>
```

### Example behavior

```js
const navbar = document.querySelector('.navbar');
const menuBtn = document.querySelector('#menu-btn');
menuBtn.addEventListener('click', () => {
	navbar.classList.toggle('active');
});
```

## Assets

Images are stored under `images/` and referenced throughout sections for visual content.

## Styling

Global styles live in `style.css`. The class `active` on `.navbar` should control visibility for small screens in your stylesheet (e.g., toggling `display`, `transform`, or `max-height`).