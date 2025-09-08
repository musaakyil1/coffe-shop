# API Reference

This project has a minimal JavaScript API focused on responsive navigation behavior.

## menuBtn click handler

- Selector: `#menu-btn`
- Behavior: Toggles the `active` class on the `.navbar` element when the menu icon is clicked.
- File: `main.js`

### Signature

This is an event listener rather than a named function. Conceptually:

```js
// Pseudocode representation
onClick(menuBtn, () => toggleClass(navbar, 'active'))
```

### Description

When the menu icon (hamburger) is clicked, the navigation bar receives or removes the `active` CSS class. This is typically used to show/hide the navigation on small screens.

### Example usage

```html
<!-- index.html -->
<i class="fa-solid fa-bars" id="menu-btn"></i>
<nav class="navbar"> ... </nav>
<script src="main.js"></script>
```

```js
// main.js
const navbar = document.querySelector('.navbar');
const menuBtn = document.querySelector('#menu-btn');

menuBtn.addEventListener('click', () => {
	navbar.classList.toggle('active');
});
```

### Expected CSS hooks

Ensure the following CSS is present to control visibility (adjust to your stylesheet):

```css
.navbar { display: none; }
.navbar.active { display: block; }
```

### Accessibility considerations

- Provide an accessible name for the menu button (e.g., `aria-label="Menu"`).
- Toggle `aria-expanded` on the button and use `aria-controls` to reference the menu.

```html
<i id="menu-btn" class="fa-solid fa-bars" aria-label="Menu" aria-expanded="false" aria-controls="primary-nav"></i>
<nav class="navbar" id="primary-nav"> ... </nav>
```

```js
menuBtn.addEventListener('click', () => {
	const expanded = menuBtn.getAttribute('aria-expanded') === 'true';
	menuBtn.setAttribute('aria-expanded', String(!expanded));
	navbar.classList.toggle('active');
});
```

---

No other public JavaScript APIs, classes, or modules are exposed in this repository.