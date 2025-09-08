# Examples

## Add a New Menu Item

```html
<div class="menu">
  <div class="box-container">
    <div class="box">
      <img src="images/menu-11.jpg" alt="menu">
      <h3>espresso special</h3>
      <div class="price">$9.99 <span>$12.99</span></div>
      <div class="btn">Buy Now</div>
    </div>
  </div>
  </div>
```

## Make the Accent Color Darker

```css
:root {
  --main-color: #b27a5c;
}
```

## Add an Alternate Menu Toggle

```html
<i class="fa-solid fa-ellipsis" id="alt-toggle"></i>
```

```js
const navbar = document.querySelector('.navbar');
document.querySelector('#alt-toggle').addEventListener('click', () => {
  navbar.classList.toggle('active');
});
```

