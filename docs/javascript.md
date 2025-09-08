## JavaScript API

File: `main.js`

This project has a single behavior: toggling the mobile navigation menu. It attaches a click event to the hamburger icon and toggles the `active` class on the navbar.

### Public Behavior
- Navbar Toggle: Adds/removes `active` on `.navbar` when `#menu-btn` is clicked.

### Source
```js
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");

menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});
```

### Usage
1. Ensure the HTML includes `#menu-btn` and `.navbar` inside `<header>`
2. Include `main.js` at the bottom of `index.html`

```html
<i class="fa-solid fa-bars" id="menu-btn"></i>
<nav class="navbar"> ... </nav>
<script src="main.js"></script>
```

### Extending Behavior
- Close menu when a link is clicked (optional):
```js
document.querySelectorAll('.navbar a').forEach((link) => {
  link.addEventListener('click', () => navbar.classList.remove('active'));
});
```

- Close menu on outside click (optional):
```js
document.addEventListener('click', (event) => {
  const isClickInside = event.target.closest('header');
  if (!isClickInside) navbar.classList.remove('active');
});
```

