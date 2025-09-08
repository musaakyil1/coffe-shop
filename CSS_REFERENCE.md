# Coffee Shop Website - CSS Reference Guide

## Overview

This comprehensive CSS reference guide documents all classes, utilities, custom properties, and styling patterns used in the Coffee Shop website. Use this guide for understanding the styling system and implementing consistent designs.

## Table of Contents

1. [CSS Custom Properties (Variables)](#css-custom-properties-variables)
2. [Global Styles](#global-styles)
3. [Utility Classes](#utility-classes)
4. [Layout Classes](#layout-classes)
5. [Component-Specific Classes](#component-specific-classes)
6. [Responsive Design](#responsive-design)
7. [Animation & Transitions](#animation--transitions)
8. [Typography System](#typography-system)

---

## CSS Custom Properties (Variables)

### Color System
**Location:** `:root` selector, lines 18-23 in `style.css`

```css
:root {
  --main-color: #d3ad7f;     /* Primary brand color (golden brown) */
  --black-color: #13131a;    /* Dark backgrounds and text */
  --bg-color: #010103;       /* Main background color (almost black) */
  --border: 0.1rem solid rgba(255, 255, 255, 0.3); /* Standard border style */
}
```

**Usage Examples:**
```css
/* Using color variables */
.element {
  background-color: var(--main-color);
  color: var(--black-color);
  border: var(--border);
}
```

**Customization:**
To change the site's color scheme, modify these variables:
```css
:root {
  --main-color: #your-primary-color;
  --black-color: #your-dark-color;
  --bg-color: #your-background-color;
  --border: 0.1rem solid rgba(255, 255, 255, 0.3);
}
```

---

## Global Styles

### Universal Reset
**Location:** Lines 5-15 in `style.css`

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  border: none;
  outline: none;
  text-decoration: none;
  list-style: none;
  text-transform: capitalize;
  transition: 0.2s linear all;
}
```

**Features:**
- Complete CSS reset for consistent cross-browser rendering
- Box-sizing set to border-box for predictable layouts
- Global transition for smooth animations
- Text-transform capitalize for consistent text styling

### Body Styles
**Location:** Lines 25-29 in `style.css`

```css
body {
  background-color: var(--bg-color);
  color: white;
  font-family: "Roboto", sans-serif;
}
```

### HTML Root Styles
**Location:** Lines 31-39 in `style.css`

```css
html {
  overflow-x: hidden;
  scroll-behavior: smooth;
  font-size: 10px; /* Base font size for rem calculations */
}
```

**Font Size System:**
- Base: 10px (makes rem calculations easy: 1.6rem = 16px)
- Mobile (800px): Inherits base size
- Small mobile (600px): 8px base

### Scrollbar Styling
**Location:** Lines 42-54 in `style.css`

```css
html::-webkit-scrollbar {
  width: 0.2rem;
}

html::-webkit-scrollbar-track {
  background-color: transparent;
}

html::-webkit-scrollbar-thumb {
  background-color: white;
  border-radius: 5rem;
}
```

---

## Utility Classes

### Button Utility (`.btn`)
**Location:** Lines 56-68 in `style.css`

```css
.btn {
  display: inline-block;
  padding: 0.9rem 3rem;
  font-size: 1.7rem;
  background-color: var(--main-color);
  color: white;
  cursor: pointer;
}

.btn:hover {
  scale: 1.1;
}
```

**Usage:**
- Primary action buttons
- Form submit buttons
- Call-to-action elements
- Navigation actions

**Variations:**
```html
<button class="btn">Button</button>
<div class="btn">Div Button</div>
<a href="#" class="btn">Link Button</a>
```

### Section Utility
**Location:** Lines 70-72 in `style.css`

```css
section {
  padding: 2rem 7%;
}
```

**Purpose:** Consistent padding for all main sections

### Heading Utility (`.heading`)
**Location:** Lines 74-84 in `style.css`

```css
.heading {
  text-align: center;
  font-size: 4rem;
  text-transform: uppercase;
  padding-bottom: 4rem;
}

.heading span {
  color: var(--main-color);
  text-transform: uppercase;
}
```

**Usage Pattern:**
```html
<h1 class="heading"><span>highlighted</span>normal text</h1>
```

---

## Layout Classes

### Grid Container (`.box-container`)
**Location:** Multiple locations in `style.css`

```css
.box-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30rem, 1fr));
  gap: 1rem; /* or 1.5rem depending on section */
}
```

**Usage:** Primary layout system for cards and items
**Responsive:** Automatically adjusts columns based on available space

### Flexbox Row (`.row`)
**Location:** Lines 158-162 in `style.css`

```css
.row {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}
```

**Common Pattern:**
```css
.row .image {
  flex: 1 1 45rem;
}

.row .content {
  flex: 1 1 45rem;
  padding: 2rem;
}
```

---

## Component-Specific Classes

### Header Styles
**Location:** Lines 87-127 in `style.css`

#### Main Header
```css
header {
  background-color: var(--bg-color);
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1.5rem 6%;
  border-bottom: var(--border);
  position: fixed;
  top: 0;
  left: 0;
  z-index: 10000;
  width: 100%;
}
```

#### Logo Styles
```css
.logo img {
  height: 6rem;
  border-radius: 50%;
}
```

#### Navigation Styles
```css
.navbar a {
  color: white;
  font-size: 1.6rem;
  margin: 0 1rem;
}

.navbar a:hover {
  color: var(--main-color);
  border-bottom: 0.1rem solid var(--main-color);
  padding-bottom: 0.5rem;
}
```

#### Icon Styles
```css
header .icons i {
  color: white;
  cursor: pointer;
  font-size: 2.5rem;
}

header .icons {
  display: none; /* Hidden on desktop, shown on mobile */
}
```

### Home Section Styles
**Location:** Lines 130-156 in `style.css`

```css
.home {
  min-height: 100vh;
  background-image: url("./images/home.jpg");
  background-position: center center;
  background-size: cover;
  display: flex;
  align-items: center;
  padding: 0 10vw;
}

.home .content {
  max-width: 60rem;
}

.home .content h3 {
  font-size: 6rem;
  text-transform: uppercase;
}

.home .content p {
  font-size: 1.5rem;
  padding: 1rem 0;
  line-height: 1.8;
  font-weight: lighter;
  color: aliceblue;
}
```

### About Section Styles
**Location:** Lines 158-185 in `style.css`

```css
.about .row {
  display: flex;
  align-items: center;
  flex-wrap: wrap;
}

.about .row .image {
  flex: 1 1 45rem;
}

.about .row .image img {
  width: 100%;
}

.about .row .content {
  flex: 1 1 45rem;
  padding: 2rem;
}

.about .row .content h3 {
  font-size: 3rem;
}

.about .row .content p {
  font-size: 1.6rem;
  padding: 1rem 0;
  line-height: 1.5;
}
```

### Menu Section Styles
**Location:** Lines 186-222 in `style.css`

```css
.menu .box-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30rem, 1fr));
  gap: 1rem;
}

.menu .box {
  border: var(--border);
  padding: 5rem;
  text-align: center;
  transition: all .4s;
}

.menu .box img {
  height: 10rem;
  width: 10rem;
  border-radius: 50%;
}

.menu .box h3 {
  font-size: 2rem;
  padding: 1rem 0;
}

.menu .box .price {
  font-size: 2.5rem;
  padding: 0.5rem;
}

.menu .box .price span {
  font-size: 1.5rem;
  font-weight: lighter;
  text-decoration: line-through;
}

.menu .box:hover {
  background-color: white;
  color: var(--black-color);
  cursor: pointer;
}
```

### Products Section Styles
**Location:** Lines 223-261 in `style.css`

```css
.products .box-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30rem, 1fr));
  gap: 1rem;
}

.products .product-box {
  border: var(--border);
  padding: 2rem;
  text-align: center;
}

.products .product-box .image {
  padding: 2rem 0;
}

.products .product-box .image img {
  height: 25rem;
  width: 25rem;
}

.products .product-box .content h3 {
  font-size: 2.5rem;
}

.products .product-box .content .stars {
  padding: 1.5rem;
}

.products .product-box .content .stars i {
  font-size: 1.7rem;
  color: var(--main-color);
}

.products .product-box .content .price {
  font-size: 2.5rem;
}

.products .product-box .content .price span {
  font-size: 1.5rem;
  text-decoration: line-through;
  font-weight: lighter;
}
```

### Reviews Section Styles
**Location:** Lines 263-294 in `style.css`

```css
.reviews .box-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30rem, 1fr));
  gap: 1.5rem;
}

.reviews .box-container .box {
  border: var(--border);
  padding: 3rem 2rem;
  text-align: center;
}

.reviews .box-container .box img {
  height: 7rem;
  width: 7rem;
  border-radius: 50%;
}

.reviews .box p {
  font-size: 1.5rem;
  line-height: 1.8;
  color: gainsboro;
  padding: 2rem 0;
}

.reviews .box h3 {
  font-size: 2rem;
  padding: 1rem 0;
}

.reviews .box .stars i {
  font-size: 1.5rem;
  color: var(--main-color);
}
```

### Contact Section Styles
**Location:** Lines 297-343 in `style.css`

```css
.contact-us .row {
  display: flex;
  background-color: var(--black-color);
  flex-wrap: wrap;
  gap: 1rem;
}

.contact-us .row form {
  flex: 1 1 45rem;
  padding: 5rem 2rem;
}

.contact-us .row .map {
  flex: 1 1 45rem;
  width: 100%;
  object-fit: cover;
}

.contact-us .row form h3 {
  text-transform: uppercase;
  font-size: 3.5rem;
}

.contact-us .row form .input-box {
  display: flex;
  align-items: center;
  margin: 2rem 0 2rem;
  background-color: var(--black-color);
  border: var(--border);
}

.contact-us .row form .input-box span {
  font-size: 2rem;
  padding-left: 2rem;
}

.contact-us .row form .input-box input {
  width: 100%;
  padding: 2rem;
  font-size: 1.7rem;
  background: none;
  color: white;
  text-transform: none;
}

.contact-us .row form .btn-container {
  display: flex;
  align-items: center;
  justify-content: center;
}

.contact-us .row form .btn-container .btn {
  width: 20rem;
}
```

### Blogs Section Styles
**Location:** Lines 344-390 in `style.css`

```css
.blogs .box-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30rem , 1fr));
  gap: 1.5rem;
}

.blogs .box-container .box {
  border: var(--border);
}

.blogs .box-container .box .image {
  width: 100%;
  height: 25rem;
  overflow: hidden;
}

.blogs .box-container .box:hover .image img {
  transform: scale(1.2);
}

.blogs .box-container .box .image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.blogs .box-container .box .content {
  padding: 2rem;
}

.blogs .box-container .box .content .title {
  color: #fff;
  font-size: 2.5rem;
  line-height: 1.5;
}

.blogs .box-container .box .content .title:hover {
  color: var(--main-color);
}

.blogs .box-container .box .content span {
  display: block;
  font-size: 1.5rem;
  padding-top: 1rem;
  color: var(--main-color);
}

.blogs .box-container .box .content p {
  font-size: 1.8rem;
  line-height: 1.8;
  color: #ccc;
  padding: 1rem 0;
}
```

### Footer Styles
**Location:** Lines 392-438 in `style.css`

```css
footer {
  background-color: var(--black-color);
  text-align: center;
}

footer .share {
  padding: 1rem 0;
}

footer .share i {
  height: 5rem;
  width: 5rem;
  font-size: 2rem;
  border: var(--border);
  border-radius: 50%;
  line-height: 5rem;
  margin: 0.4rem;
  cursor: pointer;
}

footer .share i:hover {
  background-color: var(--main-color);
}

footer .links {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  padding: 2rem 0;
  gap: 1rem;
}

footer .links a {
  padding: 0.7rem 2rem;
  color: #fff;
  font-size: 2rem;
  border: var(--border);
}

footer .links a:hover {
  background-color: var(--main-color);
}

footer .copyright {
  font-size: 2rem;
  font-weight: lighter;
  padding: 1.5rem;
}

footer .copyright span {
  color: var(--main-color);
}
```

---

## Responsive Design

### Tablet & Small Desktop (max-width: 800px)
**Location:** Lines 476-528 in `style.css`

```css
@media (max-width: 800px) {
  header {
    padding: 1.5rem 2rem;
  }
  
  header .icons {
    display: flex;
    gap: 1rem;
  }

  header .navbar {
    position: absolute;
    top: 120%;
    right: 3%;
    display: none;
    flex-direction: column;
    background-color: var(--bg-color);
    padding: 2rem;
    border-radius: 10px;
    gap: 3rem;
    text-align: center;
    box-shadow: 0 0 10px var(--main-color);
  }
  
  header .navbar.active {
    display: flex;
  }

  section {
    padding: 2rem;
  }

  .home {
    background-position: left;
    justify-content: center;
    align-items: center;
    text-align: center;
  }

  .home .content h3 {
    font-size: 4.5rem;
  }

  .about .row .content h3 {
    font-size: 2.5rem;
  }

  .about .row .content p {
    font-size: 1.3rem;
  }

  .btn-container .btn {
    width: 100% !important;
  }
}
```

### Mobile (max-width: 600px)
**Location:** Lines 530-538 in `style.css`

```css
@media (max-width: 600px) {
  html {
    font-size: 8px;
  }

  header .icons i {
    font-size: 2rem;
  }
}
```

---

## Animation & Transitions

### Global Transition
**Location:** Universal selector in `style.css`

```css
* {
  transition: 0.2s linear all;
}
```

**Purpose:** Smooth transitions for all elements

### Specific Animations

#### Button Hover Scale
```css
.btn:hover {
  scale: 1.1;
}
```

#### Menu Box Transition
```css
.menu .box {
  transition: all .4s;
}
```

#### Blog Image Scale
```css
.blogs .box:hover .image img {
  transform: scale(1.2);
}
```

#### Navigation Link Hover
```css
.navbar a:hover {
  color: var(--main-color);
  border-bottom: 0.1rem solid var(--main-color);
  padding-bottom: 0.5rem;
}
```

---

## Typography System

### Font Family
**Location:** Body styles in `style.css`

```css
body {
  font-family: "Roboto", sans-serif;
}
```

**Import:** Google Fonts Roboto
```css
@import url("https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap");
```

### Font Size Scale

#### Desktop (base: 10px)
- **Hero Title:** 6rem (60px)
- **Section Headings:** 4rem (40px)
- **About Content H3:** 3rem (30px)
- **Blog Titles:** 2.5rem (25px)
- **Product/Menu Prices:** 2.5rem (25px)
- **Product/Review Names:** 2rem (20px)
- **Menu Item Names:** 2rem (20px)
- **Footer Links:** 2rem (20px)
- **Footer Copyright:** 2rem (20px)
- **Blog Content:** 1.8rem (18px)
- **Product Stars:** 1.7rem (17px)
- **Buttons:** 1.7rem (17px)
- **Navigation:** 1.6rem (16px)
- **About Content:** 1.6rem (16px)
- **Home Content:** 1.5rem (15px)
- **Review Content:** 1.5rem (15px)
- **Review Stars:** 1.5rem (15px)
- **Blog Meta:** 1.5rem (15px)
- **Price Strikethrough:** 1.5rem (15px)

#### Mobile (800px breakpoint)
- **Hero Title:** 4.5rem (45px)
- **About Content H3:** 2.5rem (25px)
- **About Content:** 1.3rem (13px)

#### Small Mobile (600px breakpoint)
- **Base:** 8px (affects all rem values)
- **Icons:** 2rem (16px)

### Text Styling Patterns

#### Uppercase Text
```css
.heading {
  text-transform: uppercase;
}

.home .content h3 {
  text-transform: uppercase;
}
```

#### Line Heights
```css
.home .content p {
  line-height: 1.8;
}

.about .row .content p {
  line-height: 1.5;
}

.reviews .box p {
  line-height: 1.8;
}

.blogs .box-container .box .content p {
  line-height: 1.8;
}
```

#### Font Weights
```css
.home .content p {
  font-weight: lighter;
}

.footer .copyright {
  font-weight: lighter;
}

.menu .box .price span {
  font-weight: lighter;
}
```

---

## CSS Class Reference Summary

### Utility Classes
- `.btn` - Primary button styling
- `.heading` - Section headings with span highlighting
- `.box-container` - Responsive grid container
- `.row` - Flexbox row layout
- `.price` - Price display with strikethrough

### Layout Classes
- `header` - Fixed navigation header
- `section` - Standard section padding
- `footer` - Footer background and centering

### Component Classes
- `.logo` - Logo container
- `.navbar` - Navigation menu
- `.icons` - Header icon container
- `.home` - Hero section with background
- `.about` - About section layout
- `.menu` - Menu section and items
- `.products` - Products section and cards
- `.reviews` - Reviews section and testimonials
- `.contact-us` - Contact form and map
- `.blogs` - Blog section and posts

### State Classes
- `.active` - Mobile navigation active state
- `:hover` - Various hover effects

### Responsive Classes
- Media queries handle responsive behavior
- No separate responsive class system

This CSS reference provides complete documentation of all styling patterns, classes, and utilities used in the Coffee Shop website.