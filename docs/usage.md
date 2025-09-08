# Usage & Quickstart

## Quickstart

1. Open `index.html` in any modern browser.
2. Ensure `style.css` and `main.js` are in the same directory and that the `images/` folder exists.
3. The page should load with all assets. Resize the browser to test responsive behavior.

## Development

- Edit `index.html` to change content and structure.
- Edit `style.css` to update styles and responsive breakpoints.
- Edit `main.js` to customize interactivity (e.g., expand the navbar logic).

## Example: customizing the navbar toggle

Add basic accessibility attributes and refined behavior:

```html
<i id="menu-btn" class="fa-solid fa-bars" aria-label="Menu" aria-expanded="false" aria-controls="primary-nav"></i>
<nav class="navbar" id="primary-nav"> ... </nav>
```

```js
const navbar = document.querySelector('.navbar');
const menuBtn = document.querySelector('#menu-btn');
menuBtn.addEventListener('click', () => {
	const expanded = menuBtn.getAttribute('aria-expanded') === 'true';
	menuBtn.setAttribute('aria-expanded', String(!expanded));
	navbar.classList.toggle('active');
});
```

## Build & deploy

This is a static site. You can host it on any static server or CDN (e.g., GitHub Pages, Netlify, Vercel):

- Upload the files (`index.html`, `style.css`, `main.js`, `images/`).
- Configure the host to serve the root directory.