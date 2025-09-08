# JavaScript API

The site includes a minimal JavaScript behavior for the mobile navigation menu.

## Mobile Navigation Toggle

- File: `main.js`
- Behavior: Clicking the element with id `menu-btn` toggles the class `active` on the `.navbar` element.

### Signature

There is no exported function; an event listener is attached at load time:

```js
const navbar = document.querySelector('.navbar');
const menuBtn = document.querySelector('#menu-btn');

menuBtn.addEventListener('click', () => {
  navbar.classList.toggle('active');
});
```

### How It Works

- At widths below 800px, CSS hides the header navigation by default and shows it when `.navbar.active` is present.
- The event listener simply toggles that class to open/close the menu.

### Usage Example: Custom Trigger

If you add a different trigger for the menu, attach the same handler to your element:

```html
<i class="fa-solid fa-bars" id="custom-menu"></i>
```

```js
const navbar = document.querySelector('.navbar');
const customMenu = document.querySelector('#custom-menu');
customMenu.addEventListener('click', () => {
  navbar.classList.toggle('active');
});
```

