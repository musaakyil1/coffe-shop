# Coffee Shop Website - JavaScript Reference

## Overview

This document provides comprehensive documentation for all JavaScript functions, event handlers, and interactive features in the Coffee Shop website. The project uses vanilla JavaScript for lightweight, fast performance.

## Table of Contents

1. [JavaScript Architecture](#javascript-architecture)
2. [Mobile Navigation System](#mobile-navigation-system)
3. [Event Handlers](#event-handlers)
4. [DOM Manipulation](#dom-manipulation)
5. [Usage Examples](#usage-examples)
6. [Extension Guidelines](#extension-guidelines)
7. [Browser Compatibility](#browser-compatibility)

---

## JavaScript Architecture

### File Structure
- **Main File:** `main.js` (10 lines)
- **Dependencies:** None (vanilla JavaScript)
- **External Libraries:** Font Awesome (icons only)

### Code Philosophy
- **Minimal footprint:** Only essential functionality
- **No frameworks:** Pure vanilla JavaScript
- **Progressive enhancement:** Site works without JavaScript
- **Modern syntax:** ES6+ features (arrow functions, const/let)

---

## Mobile Navigation System

### Core Functionality
**Location:** Lines 1-10 in `main.js`

```javascript
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");

menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});
```

### Function Analysis

#### `document.querySelector()`
**Purpose:** DOM element selection
**Parameters:** CSS selector string
**Returns:** First matching Element or null

**Usage in Project:**
```javascript
// Select navigation menu
const navbar = document.querySelector(".navbar");

// Select menu button
const menuBtn = document.querySelector("#menu-btn");
```

**Alternative Selectors:**
```javascript
// By class
const element = document.querySelector(".className");

// By ID
const element = document.querySelector("#idName");

// By attribute
const element = document.querySelector("[data-attribute]");

// By element type
const element = document.querySelector("button");
```

#### `addEventListener()`
**Purpose:** Attach event listeners to DOM elements
**Parameters:** 
- `type` (string): Event type (e.g., 'click', 'scroll', 'resize')
- `listener` (function): Function to execute when event occurs
- `options` (optional): Event options object

**Syntax:**
```javascript
element.addEventListener('eventType', functionName);
// or
element.addEventListener('eventType', () => {
    // Event handler code
});
```

**Project Implementation:**
```javascript
menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});
```

#### `classList.toggle()`
**Purpose:** Toggle CSS class on element
**Parameters:** `className` (string) - Class name to toggle
**Returns:** Boolean indicating if class was added (true) or removed (false)

**Behavior:**
- If class exists: removes it
- If class doesn't exist: adds it

**Project Usage:**
```javascript
navbar.classList.toggle("active");
```

**Alternative classList Methods:**
```javascript
// Add class
element.classList.add("className");

// Remove class
element.classList.remove("className");

// Check if class exists
element.classList.contains("className");

// Replace class
element.classList.replace("oldClass", "newClass");
```

---

## Event Handlers

### Click Event Handler
**Function:** Mobile menu toggle
**Trigger:** Click on hamburger menu icon
**Target Element:** `#menu-btn` (hamburger icon)
**Action:** Toggle `.active` class on `.navbar`

**Complete Implementation:**
```javascript
// Element selection
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");

// Event binding
menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});
```

### Event Flow
1. **User clicks hamburger icon** (`#menu-btn`)
2. **Click event fires**
3. **Event handler executes**
4. **`classList.toggle("active")` called on navbar**
5. **CSS handles visual changes**

### CSS Integration
The JavaScript works in conjunction with CSS media queries:

```css
/* Desktop: navbar visible, icons hidden */
.navbar {
    display: flex;
}
.icons {
    display: none;
}

/* Mobile: navbar hidden by default, icons visible */
@media (max-width: 800px) {
    .navbar {
        display: none;
    }
    .icons {
        display: flex;
    }
    
    /* Show navbar when active class added by JavaScript */
    .navbar.active {
        display: flex;
    }
}
```

---

## DOM Manipulation

### Element Selection Patterns

#### Single Element Selection
```javascript
// By ID (most specific)
const menuBtn = document.querySelector("#menu-btn");

// By class (first matching element)
const navbar = document.querySelector(".navbar");

// By element type
const header = document.querySelector("header");

// Complex selectors
const firstMenuItem = document.querySelector(".navbar a:first-child");
```

#### Multiple Element Selection
```javascript
// All elements with class
const allButtons = document.querySelectorAll(".btn");

// All navigation links
const navLinks = document.querySelectorAll(".navbar a");

// All menu items
const menuItems = document.querySelectorAll(".menu .box");
```

### Class Manipulation Patterns

#### Toggle Pattern (Current Implementation)
```javascript
element.classList.toggle("active");
```

#### Add/Remove Pattern
```javascript
// Show element
element.classList.add("visible");

// Hide element
element.classList.remove("visible");
```

#### Conditional Pattern
```javascript
if (element.classList.contains("active")) {
    element.classList.remove("active");
} else {
    element.classList.add("active");
}
```

---

## Usage Examples

### Basic Mobile Menu Implementation
```javascript
// Current implementation
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");

menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});
```

### Enhanced Mobile Menu with Animation Callback
```javascript
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");

menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
    
    // Optional: Change icon based on state
    const icon = menuBtn;
    if (navbar.classList.contains("active")) {
        icon.classList.remove("fa-bars");
        icon.classList.add("fa-times");
    } else {
        icon.classList.remove("fa-times");
        icon.classList.add("fa-bars");
    }
});
```

### Close Menu When Clicking Outside
```javascript
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");
const header = document.querySelector("header");

// Toggle menu
menuBtn.addEventListener('click', (e) => {
    e.stopPropagation();
    navbar.classList.toggle("active");
});

// Close menu when clicking outside
document.addEventListener('click', (e) => {
    if (!header.contains(e.target)) {
        navbar.classList.remove("active");
    }
});
```

### Close Menu When Clicking Navigation Links
```javascript
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");
const navLinks = document.querySelectorAll(".navbar a");

// Toggle menu
menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});

// Close menu when clicking nav links
navLinks.forEach(link => {
    link.addEventListener('click', () => {
        navbar.classList.remove("active");
    });
});
```

### Smooth Scroll Navigation
```javascript
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");
const navLinks = document.querySelectorAll(".navbar a");

// Mobile menu toggle
menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});

// Smooth scroll for navigation links
navLinks.forEach(link => {
    link.addEventListener('click', (e) => {
        e.preventDefault();
        
        // Get target section
        const targetId = link.getAttribute('href');
        const targetSection = document.querySelector(targetId);
        
        if (targetSection) {
            // Smooth scroll to section
            targetSection.scrollIntoView({
                behavior: 'smooth',
                block: 'start'
            });
            
            // Close mobile menu
            navbar.classList.remove("active");
        }
    });
});
```

---

## Extension Guidelines

### Adding New Interactive Features

#### 1. Search Functionality
```javascript
const searchIcon = document.querySelector(".fa-magnifying-glass");
const searchBox = document.createElement("input");

searchIcon.addEventListener('click', () => {
    // Toggle search box visibility
    searchBox.classList.toggle("active");
});
```

#### 2. Shopping Cart Toggle
```javascript
const cartIcon = document.querySelector(".fa-cart-shopping");
const cartSidebar = document.querySelector(".cart-sidebar");

cartIcon.addEventListener('click', () => {
    cartSidebar.classList.toggle("open");
});
```

#### 3. Form Validation
```javascript
const contactForm = document.querySelector("form");
const inputs = document.querySelectorAll(".input-box input");

contactForm.addEventListener('submit', (e) => {
    e.preventDefault();
    
    let isValid = true;
    inputs.forEach(input => {
        if (!input.value.trim()) {
            input.classList.add("error");
            isValid = false;
        } else {
            input.classList.remove("error");
        }
    });
    
    if (isValid) {
        // Submit form
        console.log("Form submitted successfully");
    }
});
```

#### 4. Image Gallery/Lightbox
```javascript
const productImages = document.querySelectorAll(".product-box img");
const lightbox = document.createElement("div");

productImages.forEach(img => {
    img.addEventListener('click', () => {
        // Show image in lightbox
        lightbox.innerHTML = `<img src="${img.src}" alt="${img.alt}">`;
        lightbox.classList.add("active");
        document.body.appendChild(lightbox);
    });
});
```

#### 5. Scroll-Based Animations
```javascript
const sections = document.querySelectorAll("section");

window.addEventListener('scroll', () => {
    const scrollTop = window.pageYOffset;
    
    sections.forEach(section => {
        const sectionTop = section.offsetTop;
        const sectionHeight = section.offsetHeight;
        
        if (scrollTop >= sectionTop - window.innerHeight / 2) {
            section.classList.add("animate");
        }
    });
});
```

### Code Organization Best Practices

#### 1. Modular Structure
```javascript
// Mobile Navigation Module
const MobileNav = {
    init() {
        this.navbar = document.querySelector(".navbar");
        this.menuBtn = document.querySelector("#menu-btn");
        this.bindEvents();
    },
    
    bindEvents() {
        this.menuBtn.addEventListener('click', () => {
            this.toggleMenu();
        });
    },
    
    toggleMenu() {
        this.navbar.classList.toggle("active");
    }
};

// Initialize on DOM ready
document.addEventListener('DOMContentLoaded', () => {
    MobileNav.init();
});
```

#### 2. Event Delegation Pattern
```javascript
// Handle all button clicks with single event listener
document.addEventListener('click', (e) => {
    // Menu toggle
    if (e.target.id === 'menu-btn') {
        const navbar = document.querySelector(".navbar");
        navbar.classList.toggle("active");
    }
    
    // Buy now buttons
    if (e.target.classList.contains('btn') && e.target.textContent === 'Buy Now') {
        console.log("Add to cart functionality");
    }
    
    // Read more buttons
    if (e.target.textContent === 'read More') {
        console.log("Navigate to blog post");
    }
});
```

#### 3. Configuration Object
```javascript
const SiteConfig = {
    selectors: {
        navbar: ".navbar",
        menuBtn: "#menu-btn",
        sections: "section",
        buttons: ".btn"
    },
    
    classes: {
        active: "active",
        visible: "visible",
        hidden: "hidden"
    },
    
    animations: {
        duration: 300,
        easing: "ease-in-out"
    }
};

// Usage
const navbar = document.querySelector(SiteConfig.selectors.navbar);
navbar.classList.toggle(SiteConfig.classes.active);
```

---

## Browser Compatibility

### Modern JavaScript Features Used

#### Arrow Functions (ES6)
```javascript
// Current usage
menuBtn.addEventListener('click', () => {
    navbar.classList.toggle("active");
});

// Compatible alternative (ES5)
menuBtn.addEventListener('click', function() {
    navbar.classList.toggle("active");
});
```

#### Const/Let (ES6)
```javascript
// Current usage
const navbar = document.querySelector(".navbar");
const menuBtn = document.querySelector("#menu-btn");

// Compatible alternative (ES5)
var navbar = document.querySelector(".navbar");
var menuBtn = document.querySelector("#menu-btn");
```

### Browser Support

#### Current Implementation Support:
- **Chrome:** 51+ (arrow functions, const/let)
- **Firefox:** 45+ (arrow functions, const/let)
- **Safari:** 10+ (arrow functions, const/let)
- **Edge:** 12+ (arrow functions, const/let)
- **IE:** Not supported (arrow functions not supported)

#### Universal Compatibility Version:
```javascript
(function() {
    'use strict';
    
    var navbar = document.querySelector(".navbar");
    var menuBtn = document.querySelector("#menu-btn");
    
    if (navbar && menuBtn) {
        menuBtn.addEventListener('click', function() {
            if (navbar.classList.contains("active")) {
                navbar.classList.remove("active");
            } else {
                navbar.classList.add("active");
            }
        });
    }
})();
```

### Feature Detection
```javascript
// Check for required features
if (document.querySelector && Element.prototype.classList) {
    // Modern browser - use current implementation
    const navbar = document.querySelector(".navbar");
    const menuBtn = document.querySelector("#menu-btn");
    
    menuBtn.addEventListener('click', () => {
        navbar.classList.toggle("active");
    });
} else {
    // Fallback for older browsers
    console.warn("Browser not supported");
}
```

---

## Performance Considerations

### Current Implementation Benefits
- **Minimal code:** Only 10 lines
- **No external dependencies:** Vanilla JavaScript only
- **Event efficiency:** Single event listener
- **Memory efficient:** No memory leaks

### Optimization Tips

#### 1. Event Listener Cleanup
```javascript
// Store reference for cleanup
const handleMenuClick = () => {
    navbar.classList.toggle("active");
};

menuBtn.addEventListener('click', handleMenuClick);

// Cleanup when needed
// menuBtn.removeEventListener('click', handleMenuClick);
```

#### 2. Debounced Events
```javascript
// For scroll or resize events
function debounce(func, wait) {
    let timeout;
    return function executedFunction(...args) {
        const later = () => {
            clearTimeout(timeout);
            func(...args);
        };
        clearTimeout(timeout);
        timeout = setTimeout(later, wait);
    };
}

const handleScroll = debounce(() => {
    // Scroll handling code
}, 100);

window.addEventListener('scroll', handleScroll);
```

#### 3. Efficient DOM Queries
```javascript
// Cache DOM queries
const elements = {
    navbar: document.querySelector(".navbar"),
    menuBtn: document.querySelector("#menu-btn"),
    sections: document.querySelectorAll("section")
};

// Use cached references
elements.menuBtn.addEventListener('click', () => {
    elements.navbar.classList.toggle("active");
});
```

This JavaScript reference provides complete documentation of all interactive features and extension patterns for the Coffee Shop website.