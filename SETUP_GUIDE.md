# Coffee Shop Website - Setup & Deployment Guide

## Overview

This comprehensive guide covers everything needed to set up, customize, and deploy the Coffee Shop website. The project is built with HTML5, CSS3, and vanilla JavaScript for optimal performance and compatibility.

## Table of Contents

1. [Quick Start](#quick-start)
2. [System Requirements](#system-requirements)
3. [Local Development Setup](#local-development-setup)
4. [Project Structure](#project-structure)
5. [Configuration](#configuration)
6. [Customization Guide](#customization-guide)
7. [Deployment Options](#deployment-options)
8. [Performance Optimization](#performance-optimization)
9. [Troubleshooting](#troubleshooting)
10. [Maintenance](#maintenance)

---

## Quick Start

### 1. Download and Extract
```bash
# If using Git
git clone <repository-url>
cd coffee-shop-website

# Or download and extract ZIP file
```

### 2. Verify File Structure
Ensure you have all required files:
```
/project-folder/
├── index.html
├── main.js
├── style.css
├── README.md
├── images/
│   ├── logo.jpg
│   ├── home.jpg
│   ├── about-us.jpg
│   └── [other images...]
└── coffe shop.gif
```

### 3. Launch Website
**Option A: Direct Browser Opening**
- Double-click `index.html`
- Website opens in default browser

**Option B: Local Server (Recommended)**
```bash
# Using Python (if installed)
python -m http.server 8000
# or
python3 -m http.server 8000

# Using Node.js (if installed)
npx serve .

# Using PHP (if installed)
php -S localhost:8000
```

### 4. View Website
Open browser and navigate to:
- Direct: `file:///path/to/index.html`
- Server: `http://localhost:8000`

---

## System Requirements

### Minimum Requirements
- **Web Browser:** Chrome 51+, Firefox 45+, Safari 10+, Edge 12+
- **Screen Resolution:** 320px width minimum (mobile support)
- **Internet Connection:** Required for external resources (fonts, icons)

### Development Requirements
- **Text Editor:** VS Code, Sublime Text, Atom, or similar
- **Web Browser:** Modern browser with developer tools
- **Optional:** Local web server (Python, Node.js, or PHP)

### External Dependencies
- **Font Awesome 6.7.2:** Icons and symbols (CDN)
- **Google Fonts:** Roboto font family (CDN)
- **Google Maps:** Embedded map in contact section

---

## Local Development Setup

### Method 1: Simple File Opening
```bash
# Navigate to project directory
cd /path/to/coffee-shop-website

# Open in browser (macOS)
open index.html

# Open in browser (Windows)
start index.html

# Open in browser (Linux)
xdg-open index.html
```

### Method 2: Python HTTP Server
```bash
# Python 3
python3 -m http.server 8000

# Python 2
python -m SimpleHTTPServer 8000

# Access at http://localhost:8000
```

### Method 3: Node.js Serve
```bash
# Install serve globally
npm install -g serve

# Start server
serve -s . -l 8000

# Access at http://localhost:8000
```

### Method 4: PHP Built-in Server
```bash
# Start PHP server
php -S localhost:8000

# Access at http://localhost:8000
```

### Method 5: Live Server (VS Code)
1. Install "Live Server" extension in VS Code
2. Right-click `index.html`
3. Select "Open with Live Server"
4. Browser opens automatically with live reload

---

## Project Structure

### File Organization
```
coffee-shop-website/
├── index.html              # Main HTML file
├── main.js                 # JavaScript functionality
├── style.css               # Main stylesheet
├── README.md               # Project documentation
├── API_DOCUMENTATION.md    # API reference
├── COMPONENT_LIBRARY.md    # Component guide
├── CSS_REFERENCE.md        # CSS documentation
├── JAVASCRIPT_REFERENCE.md # JS documentation
├── SETUP_GUIDE.md          # This file
├── images/                 # Image assets
│   ├── logo.jpg           # Company logo
│   ├── home.jpg           # Hero background
│   ├── about-us.jpg       # About section image
│   ├── menu-1.jpg         # Menu item images
│   ├── menu-2.jpg         # (menu-1.jpg to menu-10.jpg)
│   ├── ...
│   ├── product-1.jpg      # Product images
│   ├── product-2.jpg      # (product-1.jpg to product-4.jpg)
│   ├── ...
│   ├── user-1.jpg         # Customer photos
│   ├── user-2.jpg         # (user-1.jpg to user-3.jpg)
│   ├── ...
│   ├── blog-1.jpg         # Blog post images
│   ├── blog-2.jpg         # (blog-1.jpg to blog-4.jpg)
│   ├── ...
│   └── other.jpg          # Additional image
└── coffe shop.gif         # Demo animation
```

### Core Files Description

#### `index.html`
- **Purpose:** Main website structure
- **Sections:** Header, Home, About, Menu, Products, Reviews, Contact, Blogs, Footer
- **Dependencies:** style.css, main.js, Font Awesome CDN, Google Fonts

#### `style.css`
- **Purpose:** Complete styling and responsive design
- **Features:** CSS Grid, Flexbox, Custom Properties, Media Queries
- **Size:** ~538 lines of CSS

#### `main.js`
- **Purpose:** Interactive functionality
- **Features:** Mobile navigation toggle
- **Size:** 10 lines of vanilla JavaScript

#### `images/`
- **Purpose:** All visual assets
- **Types:** JPEG images for photos and graphics
- **Usage:** Backgrounds, menu items, products, testimonials, blog posts

---

## Configuration

### Basic Configuration

#### 1. Site Title and Meta
Edit `index.html` head section:
```html
<head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Your Coffee Shop Name</title>
    <!-- Add meta description -->
    <meta name="description" content="Your coffee shop description">
    <!-- Add keywords -->
    <meta name="keywords" content="coffee, cafe, espresso, latte">
</head>
```

#### 2. Logo and Favicon
Replace logo files:
```html
<!-- Favicon -->
<link rel="shortcut icon" href="images/your-logo.jpg" type="image/x-icon">

<!-- Header logo -->
<img src="images/your-logo.jpg" alt="Your Coffee Shop" />
```

#### 3. Color Scheme
Edit CSS custom properties in `style.css`:
```css
:root {
  --main-color: #your-primary-color;  /* Brand color */
  --black-color: #your-dark-color;    /* Dark backgrounds */
  --bg-color: #your-bg-color;         /* Main background */
  --border: 0.1rem solid rgba(255, 255, 255, 0.3);
}
```

#### 4. Google Maps Location
Update the Google Maps embed in contact section:
```html
<iframe class="map" src="https://www.google.com/maps/embed?pb=YOUR_MAP_EMBED_CODE"></iframe>
```

**To get embed code:**
1. Go to Google Maps
2. Find your location
3. Click "Share" → "Embed a map"
4. Copy the iframe code

### Advanced Configuration

#### 1. Font Customization
Change fonts in `style.css`:
```css
/* Import new font */
@import url("https://fonts.googleapis.com/css2?family=YourFont:wght@300;400;700&display=swap");

/* Apply to body */
body {
  font-family: "YourFont", sans-serif;
}
```

#### 2. Animation Timing
Adjust global transition duration:
```css
* {
  transition: 0.3s ease-in-out all; /* Changed from 0.2s linear */
}
```

#### 3. Responsive Breakpoints
Modify breakpoints in media queries:
```css
/* Tablet breakpoint */
@media (max-width: 1024px) { /* Changed from 800px */
  /* Tablet styles */
}

/* Mobile breakpoint */
@media (max-width: 768px) { /* Changed from 600px */
  /* Mobile styles */
}
```

---

## Customization Guide

### Content Customization

#### 1. Hero Section
Edit `index.html` home section:
```html
<section class="home">
  <div class="content">
    <h3>Your Tagline Here</h3>
    <p>Your coffee shop description...</p>
    <button class="btn">Your CTA</button>
  </div>
</section>
```

Change background image in `style.css`:
```css
.home {
  background-image: url("./images/your-hero-image.jpg");
}
```

#### 2. About Section
Update content and image:
```html
<div class="content">
  <h3>Your About Title</h3>
  <p>Your story and description...</p>
  <button class="btn">Learn More</button>
</div>
```

#### 3. Menu Items
Add/modify menu items:
```html
<div class="box">
  <img src="images/your-menu-item.jpg" alt="menu item">
  <h3>Your Item Name</h3>
  <div class="price">$your.price <span>$original.price</span></div>
  <div class="btn">Buy Now</div>
</div>
```

#### 4. Contact Information
Update contact form and location:
```html
<form action="your-form-handler.php" method="POST">
  <!-- Form fields -->
</form>
```

### Visual Customization

#### 1. Image Optimization
**Recommended sizes:**
- **Logo:** 200x200px, square format
- **Hero background:** 1920x1080px or larger
- **Menu items:** 400x400px, square format
- **Products:** 500x500px, square format
- **User photos:** 300x300px, square format
- **Blog images:** 800x450px, 16:9 aspect ratio

**Optimization tools:**
- **Online:** TinyPNG, ImageOptim
- **Software:** Photoshop, GIMP
- **Format:** JPEG for photos, PNG for graphics with transparency

#### 2. Layout Modifications
**Add new section:**
```html
<section class="your-section">
  <h1 class="heading"><span>your</span>section</h1>
  <div class="box-container">
    <!-- Your content -->
  </div>
</section>
```

**Add corresponding CSS:**
```css
.your-section {
  /* Section-specific styles */
}

.your-section .box-container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(30rem, 1fr));
  gap: 1.5rem;
}
```

#### 3. Typography Adjustments
**Font sizes:**
```css
/* Adjust heading sizes */
.heading {
  font-size: 3.5rem; /* Reduced from 4rem */
}

/* Adjust body text */
.home .content p {
  font-size: 1.8rem; /* Increased from 1.5rem */
}
```

### Functionality Enhancements

#### 1. Form Handling
Add form processing:
```html
<form action="contact-handler.php" method="POST">
  <!-- Form fields -->
</form>
```

Create `contact-handler.php`:
```php
<?php
if ($_POST) {
    $name = $_POST['name'];
    $email = $_POST['email'];
    $phone = $_POST['phone'];
    
    // Process form data
    // Send email, save to database, etc.
}
?>
```

#### 2. Additional JavaScript Features
Add to `main.js`:
```javascript
// Smooth scrolling for navigation
document.querySelectorAll('.navbar a').forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault();
        const targetId = link.getAttribute('href');
        document.querySelector(targetId).scrollIntoView({
            behavior: 'smooth'
        });
    });
});

// Form validation
const form = document.querySelector('form');
form.addEventListener('submit', (e) => {
    e.preventDefault();
    // Validate form fields
    // Submit if valid
});
```

---

## Deployment Options

### Static Hosting Services

#### 1. Netlify (Recommended)
**Steps:**
1. Create account at netlify.com
2. Drag and drop project folder
3. Site deploys automatically
4. Custom domain available

**Features:**
- Free tier available
- Automatic HTTPS
- Form handling
- CDN included

#### 2. Vercel
**Steps:**
1. Create account at vercel.com
2. Connect GitHub repository or upload files
3. Automatic deployment

**Features:**
- Free tier available
- Edge network
- Automatic optimization

#### 3. GitHub Pages
**Steps:**
1. Create GitHub repository
2. Upload project files
3. Enable GitHub Pages in settings
4. Access at username.github.io/repository-name

**Requirements:**
- GitHub account
- Public repository (free tier)

#### 4. Firebase Hosting
**Steps:**
```bash
# Install Firebase CLI
npm install -g firebase-tools

# Login to Firebase
firebase login

# Initialize project
firebase init hosting

# Deploy
firebase deploy
```

### Traditional Web Hosting

#### 1. Shared Hosting
**Requirements:**
- Web hosting account with file manager or FTP access
- Upload all files to public_html or www directory

**Steps:**
1. Connect via FTP or file manager
2. Upload all project files
3. Ensure index.html is in root directory
4. Test website functionality

#### 2. VPS/Dedicated Server
**Web Server Setup (Apache):**
```bash
# Create virtual host
sudo nano /etc/apache2/sites-available/coffee-shop.conf
```

```apache
<VirtualHost *:80>
    ServerName yourdomain.com
    DocumentRoot /var/www/coffee-shop
    
    <Directory /var/www/coffee-shop>
        Options -Indexes
        AllowOverride All
        Require all granted
    </Directory>
</VirtualHost>
```

**Web Server Setup (Nginx):**
```nginx
server {
    listen 80;
    server_name yourdomain.com;
    root /var/www/coffee-shop;
    index index.html;
    
    location / {
        try_files $uri $uri/ =404;
    }
}
```

### CDN Integration

#### 1. Cloudflare Setup
1. Create Cloudflare account
2. Add your domain
3. Update nameservers
4. Enable performance features

**Benefits:**
- Global CDN
- DDoS protection
- SSL certificate
- Performance optimization

#### 2. AWS CloudFront
```bash
# Upload to S3 bucket
aws s3 sync . s3://your-bucket-name

# Create CloudFront distribution
aws cloudfront create-distribution --distribution-config file://config.json
```

---

## Performance Optimization

### Image Optimization

#### 1. Compression
**Tools:**
- **Online:** TinyPNG, Squoosh
- **CLI:** imagemin, sharp
- **Photoshop:** Save for Web

**Target sizes:**
- Hero image: < 500KB
- Menu/Product images: < 200KB
- User photos: < 100KB

#### 2. Format Selection
- **JPEG:** Photos and complex images
- **PNG:** Graphics with transparency
- **WebP:** Modern format, smaller file sizes
- **SVG:** Simple graphics and icons

#### 3. Responsive Images
Add responsive images:
```html
<img src="images/menu-item.jpg" 
     srcset="images/menu-item-small.jpg 400w,
             images/menu-item-medium.jpg 800w,
             images/menu-item-large.jpg 1200w"
     sizes="(max-width: 600px) 400px,
            (max-width: 1200px) 800px,
            1200px"
     alt="Menu Item">
```

### CSS Optimization

#### 1. Minification
**Online tools:** CSS Minifier, CleanCSS
**Build tools:** PostCSS, cssnano

**Manual minification:**
```bash
# Using cssnano (requires Node.js)
npx cssnano style.css style.min.css
```

#### 2. Critical CSS
Extract above-the-fold CSS:
```html
<style>
  /* Inline critical CSS here */
  header { /* styles */ }
  .home { /* styles */ }
</style>
<link rel="preload" href="style.css" as="style" onload="this.onload=null;this.rel='stylesheet'">
```

### JavaScript Optimization

#### 1. Minification
```javascript
// Minified version of main.js
const n=document.querySelector(".navbar"),m=document.querySelector("#menu-btn");m.addEventListener("click",()=>{n.classList.toggle("active")});
```

#### 2. Defer Loading
```html
<script src="main.js" defer></script>
```

### Loading Performance

#### 1. Preload Critical Resources
```html
<link rel="preload" href="style.css" as="style">
<link rel="preload" href="images/home.jpg" as="image">
<link rel="preload" href="https://fonts.googleapis.com/css2?family=Roboto" as="style">
```

#### 2. Lazy Loading Images
```html
<img src="images/placeholder.jpg" 
     data-src="images/actual-image.jpg" 
     loading="lazy" 
     alt="Description">
```

#### 3. Service Worker (Advanced)
Create `sw.js`:
```javascript
const CACHE_NAME = 'coffee-shop-v1';
const urlsToCache = [
  '/',
  '/style.css',
  '/main.js',
  '/images/logo.jpg'
];

self.addEventListener('install', (event) => {
  event.waitUntil(
    caches.open(CACHE_NAME)
      .then((cache) => cache.addAll(urlsToCache))
  );
});
```

---

## Troubleshooting

### Common Issues

#### 1. Images Not Loading
**Symptoms:** Broken image icons, missing visuals
**Solutions:**
- Check file paths are correct
- Verify image files exist in images/ folder
- Ensure proper file extensions (.jpg, .png)
- Check case sensitivity (Linux servers)

#### 2. Mobile Menu Not Working
**Symptoms:** Hamburger menu doesn't toggle
**Solutions:**
- Verify main.js is loaded
- Check JavaScript console for errors
- Ensure Font Awesome icons are loaded
- Test JavaScript syntax

#### 3. Fonts Not Loading
**Symptoms:** Default system fonts instead of Roboto
**Solutions:**
- Check internet connection
- Verify Google Fonts URL is correct
- Test with different CDN
- Add fallback fonts

#### 4. CSS Styles Not Applied
**Symptoms:** Unstyled HTML, broken layout
**Solutions:**
- Check style.css path in HTML
- Verify CSS syntax
- Clear browser cache
- Check for conflicting styles

#### 5. Responsive Issues
**Symptoms:** Layout breaks on mobile/tablet
**Solutions:**
- Test media queries
- Check viewport meta tag
- Verify grid/flexbox properties
- Test on actual devices

### Debugging Tools

#### 1. Browser Developer Tools
**Chrome DevTools:**
- F12 or right-click → Inspect
- Check Console for JavaScript errors
- Use Network tab for loading issues
- Test responsive design

#### 2. Validation Tools
**HTML Validator:**
- W3C Markup Validator
- Check for syntax errors

**CSS Validator:**
- W3C CSS Validator
- Verify CSS syntax

#### 3. Performance Testing
**Tools:**
- Google PageSpeed Insights
- GTmetrix
- WebPageTest
- Lighthouse (built into Chrome)

### Error Messages

#### "Failed to load resource"
**Cause:** Missing files or incorrect paths
**Solution:** Check file paths and ensure files exist

#### "Uncaught ReferenceError"
**Cause:** JavaScript variable/function not found
**Solution:** Check JavaScript syntax and variable names

#### "404 Not Found"
**Cause:** Server cannot find requested file
**Solution:** Verify file paths and server configuration

---

## Maintenance

### Regular Updates

#### 1. Content Updates
**Monthly tasks:**
- Update menu items and prices
- Add new blog posts
- Update customer reviews
- Refresh product images

#### 2. Security Updates
**Quarterly tasks:**
- Update CDN links (Font Awesome, Google Fonts)
- Check for broken external links
- Review and update contact information
- Test form functionality

#### 3. Performance Monitoring
**Tools to monitor:**
- Google Analytics for traffic
- Google Search Console for SEO
- PageSpeed Insights for performance
- Uptime monitoring services

### Backup Strategy

#### 1. File Backup
**Regular backups:**
- Download complete website files
- Store in version control (Git)
- Keep local copies of images
- Document changes and updates

#### 2. Version Control
```bash
# Initialize Git repository
git init

# Add all files
git add .

# Commit changes
git commit -m "Initial website setup"

# Add remote repository
git remote add origin <repository-url>

# Push to remote
git push -u origin main
```

### SEO Maintenance

#### 1. Meta Tags
```html
<meta name="description" content="Best coffee shop in [city] - Fresh roasted beans, artisan drinks">
<meta name="keywords" content="coffee, cafe, [city], espresso, latte">
<meta property="og:title" content="Coffee Shop Name">
<meta property="og:description" content="Your description">
<meta property="og:image" content="images/logo.jpg">
```

#### 2. Structured Data
Add JSON-LD for local business:
```html
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "CafeOrCoffeeShop",
  "name": "Your Coffee Shop",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main St",
    "addressLocality": "City",
    "addressRegion": "State",
    "postalCode": "12345"
  },
  "telephone": "+1-555-123-4567"
}
</script>
```

### Analytics Setup

#### 1. Google Analytics
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

#### 2. Search Console
1. Add and verify your site
2. Submit sitemap.xml
3. Monitor search performance
4. Fix crawl errors

This comprehensive setup guide provides everything needed to successfully deploy and maintain the Coffee Shop website.