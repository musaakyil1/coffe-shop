## Components

This project uses class-based HTML components styled in `style.css`.

### Button (`.btn`)
Reusable call-to-action button.

Markup:
```html
<button class="btn">Get Yours Now</button>
```

Behavior:
- Hover scale effect
- In forms, pair with `.btn-container` for centering

### Heading (`.heading`)
Section titles with an accent span.

Markup:
```html
<h1 class="heading"><span>our</span> products</h1>
```

### Navbar (`header .navbar`)
Primary navigation; toggled on mobile via `active` class.

Structure:
```html
<nav class="navbar">
  <a href="#">Home</a>
  <a href="#">About</a>
  <!-- ... -->
  <a href="#blogs">blogs</a>
  <!-- Add new links as needed -->
  
</nav>
```

Mobile state:
```html
<!-- .navbar.active is added/removed by JavaScript -->
```

### Menu Card (`.menu .box`)
Displays a menu item with image, title, price, and action.

Markup:
```html
<div class="box">
  <img src="images/menu-1.jpg" alt="menu" />
  <h3>tasty and healthy</h3>
  <div class="price">$14.99 <span>$19.99</span></div>
  <div class="btn">Buy Now</div>
</div>
```

### Product Card (`.products .product-box`)
Displays a product with image, title, rating stars, and price.

Markup:
```html
<div class="product-box">
  <div class="image"><img src="images/product-1.jpg" alt="products" /></div>
  <div class="content">
    <h3>Fresh Coffee</h3>
    <div class="stars">
      <i class="fa-solid fa-star"></i>
      <i class="fa-solid fa-star"></i>
      <i class="fa-solid fa-star"></i>
      <i class="fa-solid fa-star"></i>
      <i class="fa-solid fa-star"></i>
    </div>
    <div class="price">$12.99 <span>$19.99</span></div>
  </div>
</div>
```

### Review Card (`.reviews .box`)
Customer review with text, avatar, name, and stars.

Markup:
```html
<div class="box">
  <p>Review text...</p>
  <img src="images/user-1.jpg" alt="user" />
  <h3>Jane D.</h3>
  <div class="stars">
    <i class="fa-solid fa-star"></i>
    <i class="fa-solid fa-star"></i>
    <i class="fa-solid fa-star"></i>
    <i class="fa-solid fa-star"></i>
    <i class="fa-solid fa-star"></i>
  </div>
</div>
```

### Blog Card (`.blogs .box`)
Blog teaser with image, title link, meta, and excerpt.

Markup:
```html
<div class="box">
  <div class="image"><img src="images/blog-1.jpg" alt="blog" /></div>
  <div class="content">
    <a href="#" class="title">tasty and refreshing</a>
    <span>by admin / 22.10.2025</span>
    <p>Excerpt...</p>
    <button class="btn">read More</button>
  </div>
</div>
```

### Contact Form (`.contact-us form`)
Contact form layout with icon inputs and submit button.

Markup:
```html
<form>
  <h3>get in touch</h3>
  <div class="input-box">
    <span><i class="fa-solid fa-user"></i></span>
    <input type="text" placeholder="name" />
  </div>
  <div class="input-box">
    <span><i class="fa-solid fa-envelope"></i></span>
    <input type="email" placeholder="email" />
  </div>
  <div class="input-box">
    <span><i class="fa-solid fa-phone"></i></span>
    <input type="number" placeholder="phone" />
  </div>
  <div class="btn-container">
    <button class="btn">send</button>
  </div>
</form>
```

