# Coffee Shop Website – Comprehensive Documentation

## Table of Contents
1. Introduction
2. Getting Started
3. Project Structure
4. Public APIs
5. JavaScript Functions
6. HTML Components / Sections
7. CSS Utility Classes & Variables
8. Assets (Images & GIFs)
9. Customisation Guide
10. FAQ
11. Contributing
12. License

---

## 1. Introduction
This documentation provides an in-depth overview of every public facing API, function and UI component that ships with the **Coffee Shop** website. It is targeted at developers who would like to:
- Understand how the site works under the hood.
- Integrate additional JavaScript logic (e.g. analytics, e-commerce hooks).
- Customise the look & feel (colours, fonts, layout).

> 📌  **Live demo:** Open `index.html` directly in any modern browser or serve the project with your favourite static-site server.

---

## 2. Getting Started
1. **Clone / Download** the repository.
2. **Install dependencies (optional).** This project is fully static, so no build step is required. If you wish to use a local dev server, run:
   ```bash
   npx serve .   # or python -m http.server
   ```
3. **Open** `http://localhost:<port>` in your browser.

---

## 3. Project Structure
```text
/ (project root)
|-- index.html        # Main HTML entry point
|-- style.css         # Global stylesheet
|-- main.js           # JavaScript (NavBar toggle logic)
|-- images/           # All image assets
|-- DOCUMENTATION.md  # ← You are here
|-- README.md         # TL;DR overview (Turkish)
```

---

## 4. Public APIs
The site exposes a **minimal JavaScript API** designed for extensibility. Currently there is **one public function** that can be consumed by third-party scripts.

| Function | Location | Description |
| -------- | -------- | ----------- |
| `toggleNavbar()` | `main.js` | Programmatically toggles the visibility of the responsive navigation bar. |

### 4.1 Usage Example
```html
<!-- Load site scripts as usual -->
<script src="main.js"></script>
<script>
  // Wait for the DOM to be fully parsed
  window.addEventListener('DOMContentLoaded', () => {
      // Toggle navbar every 5 seconds
      setInterval(toggleNavbar, 5000);
  });
</script>
```
> The function is globally available because `main.js` attaches it to the `window` object (see implementation below).

---

## 5. JavaScript Functions
Below is a documentation block generated from the current contents of `main.js`.

### 5.1 `toggleNavbar()`
```js
function toggleNavbar () {
  const navbar = document.querySelector('.navbar');
  navbar.classList.toggle('active');
}
```
* **Parameters:** none
* **Returns:** `void`
* **Side-effects:** Adds or removes the `active` class on the `.navbar` element, which shows/hides the mobile menu via CSS.
* **Usage scenarios:**
  * Burger-button (`#menu-btn`) click handler (default).
  * Programmatic control from custom modules (see §4.1).

### 5.2 Event Bindings
```js
menuBtn.addEventListener('click', toggleNavbar);
```
* **Element:** `<i class="fa-solid fa-bars" id="menu-btn"></i>`
* **Purpose:** Toggling the navbar on small screens.

---

## 6. HTML Components / Sections
The single-page layout is divided into semantic `<section>` blocks. Each carries a distinguishing class for styling and anchor links:

| Section | Selector | Purpose |
| ------- | -------- | ------- |
| Header  | `header` | Sticky top navigation containing logo, links & icons. |
| Home    | `.home` | Hero banner with marketing tagline and CTA button. |
| About   | `.about` | Brief story plus imagery. |
| Menu    | `.menu` | Product grid with pricing. |
| Products| `.products` | Highlighted best-sellers. |
| Reviews | `.reviews` | Customer testimonials carousel/grid. |
| Contact | `.contact-us` | Embedded map & contact form. |
| Blogs   | `.blogs` | Latest news articles. |
| Footer  | `footer` | Social media links & copyright. |

### 6.1 Component Example – Menu Card
```html
<div class="box">
  <img src="images/menu-1.jpg" alt="menu">
  <h3>tasty and healthy</h3>
  <div class="price">$14.99 <span>$19.99</span></div>
  <div class="btn">Buy Now</div>
</div>
```
* **`img`** – product photo.
* **`h3`** – title.
* **`.price`** – current & old price.
* **`.btn`** – primary action; style defined in `style.css`.

---

## 7. CSS Utility Classes & Variables
Key reusable classes:
* `.btn` – Main call-to-action button with hover transition.
* `.heading` – Section headers (`<h1>`). Uses `span` to highlight words.
* `.box-container` – Flexbox wrapper for equal-width children.
* `.active` – Toggled state for responsive navbar.

You can override colours & spacing at the top of `style.css`:
```css
:root {
  --primary: #c59d5f;
  --dark: #13131a;
  --light: #ffffff;
  /* ... */
}
```

---

## 8. Assets (Images & GIFs)
All images are stored under `/images`.

| File | Usage |
| ---- | ----- |
| `logo.jpg` | Navbar logo & favicon. |
| `menu-*.jpg` | Product thumbnails. |
| `product-*.jpg` | Featured products grid. |
| `blog-*.jpg` | Blog thumbnails. |
| `user-*.jpg` | Customer avatars. |
| `about-us.jpg` | About section. |
| `home.jpg` / `coffe shop.gif` | Hero imagery/background. |

> Replace or compress images to optimise load times.

---

## 9. Customisation Guide
| Task | How-To |
| ---- | ------ |
| Update site colours | Edit CSS variables in `style.css` → `:root` block. |
| Change navigation links | Modify `<nav class="navbar">` inside `index.html`. |
| Add new menu item | Duplicate a `.box` within `.menu .box-container`. |
| Hook into navbar toggle | Call `toggleNavbar()` directly. |
| Add analytics | Create a new `<script>` tag after `main.js`. |

---

## 10. FAQ
**Q:** How can I preload images to avoid layout shifts?<br>
**A:** Add `link rel="preload" as="image" href="/images/..."` inside `<head>`.

**Q:** Does the site support IE11? <br>
**A:** Modern CSS features (flexbox gaps, CSS variables) are used, so legacy browsers are not supported out-of-the-box.

---

## 11. Contributing
1. Fork the repo.
2. Create a new branch: `git checkout -b feature/my-feature`.
3. Commit your changes: `git commit -m "feat: add my feature"`.
4. Push branch & open a Pull Request.

---

## 12. License
This project is licensed under the MIT License. See `LICENSE` file for details.