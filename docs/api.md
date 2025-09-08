## JavaScript API Reference

The project exposes one behavior via `main.js` that controls the responsive navigation menu.

### toggleMobileNavbar

Implicit function provided by event listener on the menu button. When the button with id `menu-btn` is clicked, the script toggles the `active` class on the element with class `navbar`.

Source:

```1:7:/workspace/main.js
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");



menuBtn.addEventListener('click',() =>{
    navbar.classList.toggle("active");
});
```

#### Usage

- Ensure your HTML has a navigation element with class `navbar` and a button/icon with id `menu-btn`.
- Include `main.js` at the end of `body`.

Example HTML snippet:

```html
<header>
  <nav class="navbar">
    <a href="#">Home</a>
    <!-- other links -->
  </nav>
  <div class="icons">
    <i class="fa-solid fa-bars" id="menu-btn"></i>
  </div>
  
  <!-- ... -->
</header>
<script src="main.js"></script>
```

Behavior:

- On narrow viewports (see media queries in `style.css`), `.navbar` is hidden by default. When `.navbar.active` is present, it becomes visible as a column menu.

#### Notes

- No globals are exported; behavior is attached via DOM event listeners.
- Modify selectors in `main.js` if you change class/id names.
