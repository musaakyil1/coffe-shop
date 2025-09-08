# Coffee Shop Website - Component Library

## Overview

This document provides detailed examples and usage instructions for all reusable components in the Coffee Shop website. Each component includes HTML structure, CSS classes, customization options, and implementation examples.

## Table of Contents

1. [Button Components](#button-components)
2. [Card Components](#card-components)
3. [Form Components](#form-components)
4. [Layout Components](#layout-components)
5. [Navigation Components](#navigation-components)
6. [Content Components](#content-components)
7. [Interactive Components](#interactive-components)

---

## Button Components

### Primary Button (`.btn`)

**Purpose:** Main call-to-action buttons throughout the site.

**HTML Structure:**
```html
<button class="btn">Button Text</button>
<!-- or -->
<div class="btn">Button Text</div>
<!-- or -->
<a href="#" class="btn">Button Text</a>
```

**CSS Properties:**
```css
.btn {
  display: inline-block;
  padding: 0.9rem 3rem;
  font-size: 1.7rem;
  background-color: var(--main-color);
  color: white;
  cursor: pointer;
}
```

**Usage Examples:**

1. **Hero Section CTA:**
```html
<button class="btn">Get Yours Now</button>
```

2. **About Section Learn More:**
```html
<button class="btn">Learn More</button>
```

3. **Menu Item Purchase:**
```html
<div class="btn">Buy Now</div>
```

4. **Contact Form Submit:**
```html
<button class="btn">send</button>
```

5. **Blog Read More:**
```html
<button class="btn">read More</button>
```

**Customization:**
- Change background color by modifying `--main-color` CSS variable
- Adjust padding for different sizes
- Modify font-size for different text scales

**Responsive Behavior:**
- On mobile (max-width: 800px), buttons in `.btn-container` become full width
- Hover effect scales button to 1.1x size

---

## Card Components

### Menu Item Card (`.box`)

**Purpose:** Display menu items with image, title, and pricing.

**HTML Structure:**
```html
<div class="box">
  <img src="images/menu-item.jpg" alt="menu item">
  <h3>Item Name</h3>
  <div class="price">$14.99 <span>$19.99</span></div>
  <div class="btn">Buy Now</div>
</div>
```

**Container:**
```html
<div class="box-container">
  <!-- Multiple .box elements -->
</div>
```

**CSS Classes:**
- `.box` - Individual menu item container
- `.price` - Price display with strikethrough original price
- `.box:hover` - White background on hover

**Usage Example:**
```html
<section class="menu">
  <h1 class="heading"><span>our</span>menu</h1>
  <div class="box-container">
    <div class="box">
      <img src="images/espresso.jpg" alt="espresso">
      <h3>Premium Espresso</h3>
      <div class="price">$3.99 <span>$5.99</span></div>
      <div class="btn">Buy Now</div>
    </div>
    <div class="box">
      <img src="images/latte.jpg" alt="latte">
      <h3>Caramel Latte</h3>
      <div class="price">$4.99 <span>$6.99</span></div>
      <div class="btn">Buy Now</div>
    </div>
  </div>
</section>
```

### Product Card (`.product-box`)

**Purpose:** Showcase products with detailed information and ratings.

**HTML Structure:**
```html
<div class="product-box">
  <div class="image">
    <img src="images/product.jpg" alt="product">
  </div>
  <div class="content">
    <h3>Product Name</h3>
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

**CSS Classes:**
- `.product-box` - Main product container
- `.image` - Product image wrapper
- `.content` - Product information container
- `.stars` - Star rating display

**Usage Example:**
```html
<section class="products">
  <h1 class="heading"><span>our</span>products</h1>
  <div class="box-container">
    <div class="product-box">
      <div class="image">
        <img src="images/coffee-beans.jpg" alt="coffee beans">
      </div>
      <div class="content">
        <h3>Premium Coffee Beans</h3>
        <div class="stars">
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
          <i class="fa-solid fa-star"></i>
        </div>
        <div class="price">$24.99 <span>$34.99</span></div>
      </div>
    </div>
  </div>
</section>
```

### Review Card (`.box` in reviews context)

**Purpose:** Display customer testimonials with photos and ratings.

**HTML Structure:**
```html
<div class="box">
  <p>Customer review text goes here...</p>
  <img src="images/customer.jpg" alt="customer">
  <h3>Customer Name</h3>
  <div class="stars">
    <i class="fa-solid fa-star"></i>
    <i class="fa-solid fa-star"></i>
    <i class="fa-solid fa-star"></i>
    <i class="fa-solid fa-star"></i>
    <i class="fa-solid fa-star"></i>
  </div>
</div>
```

**Usage Example:**
```html
<section class="reviews">
  <h1 class="heading"><span>customer's</span>reviews</h1>
  <div class="box-container">
    <div class="box">
      <p>"Absolutely love the coffee here! The atmosphere is perfect for working and the baristas are incredibly skilled. Highly recommend the caramel macchiato!"</p>
      <img src="images/sarah-customer.jpg" alt="Sarah">
      <h3>Sarah Johnson</h3>
      <div class="stars">
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
        <i class="fa-solid fa-star"></i>
      </div>
    </div>
  </div>
</section>
```

### Blog Card (`.box` in blogs context)

**Purpose:** Display blog posts with images, titles, and excerpts.

**HTML Structure:**
```html
<div class="box">
  <div class="image">
    <img src="images/blog-post.jpg" alt="blog post">
  </div>
  <div class="content">
    <a href="#" class="title">Blog Post Title</a>
    <span>by author / date</span>
    <p>Blog post excerpt or description...</p>
    <button class="btn">read More</button>
  </div>
</div>
```

**CSS Classes:**
- `.image` - Blog post image container with hover effect
- `.title` - Blog post title link
- `.content` - Blog post text content

**Usage Example:**
```html
<section class="blogs">
  <h1 class="heading">our <span>blogs</span></h1>
  <div class="box-container">
    <div class="box">
      <div class="image">
        <img src="images/coffee-brewing-guide.jpg" alt="coffee brewing">
      </div>
      <div class="content">
        <a href="#" class="title">The Ultimate Coffee Brewing Guide</a>
        <span>by Coffee Expert / 15.01.2024</span>
        <p>Discover the secrets to brewing the perfect cup of coffee at home. From bean selection to water temperature, we cover everything you need to know.</p>
        <button class="btn">read More</button>
      </div>
    </div>
  </div>
</section>
```

---

## Form Components

### Input Box (`.input-box`)

**Purpose:** Styled form input fields with icons.

**HTML Structure:**
```html
<div class="input-box">
  <span><i class="fa-solid fa-icon-name"></i></span>
  <input type="text" placeholder="placeholder text">
</div>
```

**CSS Classes:**
- `.input-box` - Container for input and icon
- `span` - Icon container
- `input` - Styled input field

**Available Input Types:**

1. **Name Input:**
```html
<div class="input-box">
  <span><i class="fa-solid fa-user"></i></span>
  <input type="text" placeholder="Full Name">
</div>
```

2. **Email Input:**
```html
<div class="input-box">
  <span><i class="fa-solid fa-envelope"></i></span>
  <input type="email" placeholder="Email Address">
</div>
```

3. **Phone Input:**
```html
<div class="input-box">
  <span><i class="fa-solid fa-phone"></i></span>
  <input type="tel" placeholder="Phone Number">
</div>
```

4. **Message/Textarea:**
```html
<div class="input-box">
  <span><i class="fa-solid fa-message"></i></span>
  <textarea placeholder="Your Message" rows="5"></textarea>
</div>
```

### Contact Form (Complete Example)

**HTML Structure:**
```html
<form>
  <h3>get in touch</h3>
  <div class="input-box">
    <span><i class="fa-solid fa-user"></i></span>
    <input type="text" placeholder="name" required>
  </div>
  <div class="input-box">
    <span><i class="fa-solid fa-envelope"></i></span>
    <input type="email" placeholder="email" required>
  </div>
  <div class="input-box">
    <span><i class="fa-solid fa-phone"></i></span>
    <input type="tel" placeholder="phone">
  </div>
  <div class="input-box">
    <span><i class="fa-solid fa-message"></i></span>
    <textarea placeholder="message" rows="5"></textarea>
  </div>
  <div class="btn-container">
    <button type="submit" class="btn">send message</button>
  </div>
</form>
```

---

## Layout Components

### Section Container

**Purpose:** Standard section wrapper with consistent padding.

**HTML Structure:**
```html
<section class="section-name">
  <!-- Section content -->
</section>
```

**CSS Properties:**
```css
section {
  padding: 2rem 7%;
}
```

### Grid Container (`.box-container`)

**Purpose:** Responsive grid layout for cards and items.

**HTML Structure:**
```html
<div class="box-container">
  <!-- Grid items -->
</div>
```

**CSS Properties:**
```css
.box-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30rem, 1fr));
  gap: 1rem;
}
```

**Usage Examples:**

1. **Three-Column Grid:**
```html
<div class="box-container">
  <div class="box">Item 1</div>
  <div class="box">Item 2</div>
  <div class="box">Item 3</div>
</div>
```

2. **Responsive Product Grid:**
```html
<div class="box-container">
  <div class="product-box">Product 1</div>
  <div class="product-box">Product 2</div>
  <div class="product-box">Product 3</div>
  <div class="product-box">Product 4</div>
</div>
```

### Two-Column Row (`.row`)

**Purpose:** Flexible two-column layout for content and images.

**HTML Structure:**
```html
<div class="row">
  <div class="image">
    <img src="image.jpg" alt="description">
  </div>
  <div class="content">
    <h3>Content Title</h3>
    <p>Content text...</p>
    <button class="btn">Action Button</button>
  </div>
</div>
```

**CSS Properties:**
```css
.row {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.row .image {
  flex: 1 1 45rem;
}

.row .content {
  flex: 1 1 45rem;
  padding: 2rem;
}
```

---

## Navigation Components

### Header Navigation

**Purpose:** Main site navigation with logo and menu items.

**HTML Structure:**
```html
<header>
  <a class="logo" href="#">
    <img src="images/logo.jpg" alt="Company Logo" />
  </a>
  <nav class="navbar">
    <a href="#home">Home</a>
    <a href="#about">About</a>
    <a href="#menu">Menu</a>
    <a href="#products">Products</a>
    <a href="#reviews">Reviews</a>
    <a href="#contact">Contact</a>
    <a href="#blogs">Blogs</a>
  </nav>
  <div class="icons">
    <i class="fa-solid fa-magnifying-glass"></i>
    <i class="fa-solid fa-cart-shopping"></i>
    <i class="fa-solid fa-bars" id="menu-btn"></i>
  </div>
</header>
```

**Features:**
- Fixed positioning
- Mobile-responsive toggle menu
- Hover effects on navigation links
- Icon-based actions (search, cart, menu)

### Footer Navigation

**Purpose:** Footer links and social media integration.

**HTML Structure:**
```html
<footer>
  <section>
    <div class="share">
      <i class="fa-brands fa-facebook"></i>
      <i class="fa-brands fa-instagram"></i>
      <i class="fa-brands fa-x-twitter"></i>
      <i class="fa-brands fa-pinterest"></i>
      <i class="fa-brands fa-linkedin"></i>
    </div>
    <div class="links">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#menu">Menu</a>
      <a href="#products">Products</a>
      <a href="#reviews">Reviews</a>
      <a href="#contact">Contact</a>
      <a href="#blogs">Blogs</a>
    </div>
    <div class="copyright">
      created by <span>Your Name</span> all rights reserved
    </div>
  </section>
</footer>
```

---

## Content Components

### Section Heading (`.heading`)

**Purpose:** Consistent section titles with highlighted spans.

**HTML Structure:**
```html
<h1 class="heading"><span>highlighted</span>text</h1>
<!-- or -->
<h1 class="heading">text<span>highlighted</span></h1>
```

**Usage Examples:**

1. **About Section:**
```html
<h1 class="heading"><span>about</span>us</h1>
```

2. **Menu Section:**
```html
<h1 class="heading"><span>our</span>menu</h1>
```

3. **Products Section:**
```html
<h1 class="heading"><span>our</span>products</h1>
```

4. **Reviews Section:**
```html
<h1 class="heading"><span>customer's</span>reviews</h1>
```

### Hero Section (`.home`)

**Purpose:** Full-screen hero section with background image.

**HTML Structure:**
```html
<section class="home">
  <div class="content">
    <h3>Main Headline</h3>
    <p>Supporting description text...</p>
    <button class="btn">Call to Action</button>
  </div>
</section>
```

**Customization:**
- Change background image in CSS: `background-image: url("./images/your-image.jpg")`
- Modify content positioning and styling
- Adjust text content and CTA button

### Star Rating Component (`.stars`)

**Purpose:** Display star ratings for products and reviews.

**HTML Structure:**
```html
<div class="stars">
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
</div>
```

**Variations:**

1. **5-Star Rating:**
```html
<div class="stars">
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
</div>
```

2. **4-Star Rating:**
```html
<div class="stars">
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-regular fa-star"></i>
</div>
```

3. **3.5-Star Rating:**
```html
<div class="stars">
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star"></i>
  <i class="fa-solid fa-star-half-stroke"></i>
  <i class="fa-regular fa-star"></i>
</div>
```

### Price Display (`.price`)

**Purpose:** Show current and original prices with strikethrough.

**HTML Structure:**
```html
<div class="price">$current.price <span>$original.price</span></div>
```

**Usage Examples:**

1. **Menu Item Pricing:**
```html
<div class="price">$14.99 <span>$19.99</span></div>
```

2. **Product Pricing:**
```html
<div class="price">$24.99 <span>$34.99</span></div>
```

---

## Interactive Components

### Mobile Menu Toggle

**Purpose:** JavaScript-powered mobile navigation toggle.

**HTML Requirements:**
```html
<!-- Menu button -->
<i class="fa-solid fa-bars" id="menu-btn"></i>

<!-- Navigation menu -->
<nav class="navbar">
  <!-- Navigation items -->
</nav>
```

**JavaScript Implementation:**
```javascript
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");

menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});
```

**CSS Requirements:**
```css
@media (max-width: 800px) {
  .navbar {
    display: none;
    /* Hidden by default on mobile */
  }
  
  .navbar.active {
    display: flex;
    /* Shown when active class is toggled */
  }
}
```

### Hover Effects

**Purpose:** Interactive hover states for better user experience.

**Available Hover Effects:**

1. **Button Hover:**
```css
.btn:hover {
  scale: 1.1;
}
```

2. **Navigation Link Hover:**
```css
.navbar a:hover {
  color: var(--main-color);
  border-bottom: 0.1rem solid var(--main-color);
  padding-bottom: 0.5rem;
}
```

3. **Menu Box Hover:**
```css
.menu .box:hover {
  background-color: white;
  color: var(--black-color);
  cursor: pointer;
}
```

4. **Blog Image Hover:**
```css
.blogs .box:hover .image img {
  transform: scale(1.2);
}
```

5. **Social Icon Hover:**
```css
footer .share i:hover {
  background-color: var(--main-color);
}
```

---

## Component Usage Guidelines

### Best Practices

1. **Consistent Structure:** Always follow the established HTML structure for each component
2. **Semantic HTML:** Use appropriate HTML elements (buttons for actions, links for navigation)
3. **Accessibility:** Include proper alt text for images and ARIA labels where needed
4. **Responsive Design:** Test components on different screen sizes
5. **Performance:** Optimize images and minimize CSS/JS when possible

### Common Patterns

1. **Section Pattern:**
```html
<section class="section-name">
  <h1 class="heading"><span>highlighted</span>text</h1>
  <div class="box-container">
    <!-- Grid items -->
  </div>
</section>
```

2. **Card Pattern:**
```html
<div class="box">
  <img src="image.jpg" alt="description">
  <h3>Title</h3>
  <p>Description</p>
  <div class="btn">Action</div>
</div>
```

3. **Form Pattern:**
```html
<form>
  <h3>form title</h3>
  <div class="input-box">
    <span><i class="icon"></i></span>
    <input type="text" placeholder="placeholder">
  </div>
  <div class="btn-container">
    <button class="btn">submit</button>
  </div>
</form>
```

### Customization Tips

1. **Colors:** Modify CSS custom properties in `:root` for global color changes
2. **Spacing:** Adjust padding and margins consistently across components
3. **Typography:** Use the established font sizes and weights for consistency
4. **Images:** Maintain consistent aspect ratios within component types
5. **Animations:** Keep transition durations consistent (0.2s linear is used throughout)

This component library provides all the building blocks needed to create additional pages or modify existing sections while maintaining design consistency and functionality.