## Usage Examples

### Add a New Menu Item
```html
<div class="menu">
  <div class="box-container">
    <div class="box">
      <img src="images/menu-11.jpg" alt="menu" />
      <h3>espresso</h3>
      <div class="price">$3.99 <span>$4.99</span></div>
      <div class="btn">Buy Now</div>
    </div>
  </div>
  
</div>
```

### Add a New Product
```html
<div class="products">
  <div class="box-container">
    <div class="product-box">
      <div class="image"><img src="images/product-5.jpg" alt="products" /></div>
      <div class="content">
        <h3>Arabica Beans</h3>
        <div class="stars">
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
        </div>
        <div class="price">$15.99 <span>$21.99</span></div>
      </div>
    </div>
  </div>
  
</div>
```

### Add a Blog Card
```html
<div class="blogs">
  <div class="box-container">
    <div class="box">
      <div class="image"><img src="images/blog-5.jpg" alt="logo" /></div>
      <div class="content">
        <a href="#" class="title">summer cold brew tips</a>
        <span>by admin / 01.08.2025</span>
        <p>Simple steps to brew refreshing cold coffee at home.</p>
        <button class="btn">read More</button>
      </div>
    </div>
  </div>
  
</div>
```

### Make Navbar Links Scroll to Sections
```html
<!-- Give sections IDs and point links to them -->
<nav class="navbar">
  <a href="#home">Home</a>
  <a href="#about">About</a>
  <a href="#menu">menu</a>
  <a href="#products">products</a>
  <a href="#reviews">reviews</a>
  <a href="#contact-us">contact</a>
  <a href="#blogs">blogs</a>
</nav>

<section id="home" class="home">...</section>
<section id="about" class="about">...</section>
<section id="menu" class="menu">...</section>
<section id="products" class="products">...</section>
<section id="reviews" class="reviews">...</section>
<section id="blogs" class="blogs">...</section>
```

### Close Mobile Menu on Link Click
```js
// Add to main.js
document.querySelectorAll('.navbar a').forEach((link) => {
  link.addEventListener('click', () =>
    document.querySelector('.navbar').classList.remove('active')
  );
});
```

