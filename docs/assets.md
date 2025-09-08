## Assets

All images are located in the `images/` directory and are referenced directly from HTML and CSS.

### Folders
- `images/`: Contains logos, section images, product images, menu thumbnails, blog images, and user avatars.

### Referencing Images
```html
<img src="images/logo.jpg" alt="logo" />
<img src="images/menu-1.jpg" alt="menu" />
```

In CSS:
```css
.home {
  background-image: url("./images/home.jpg");
}
```

### Performance Tips
- Use optimized JPG/PNG/WebP where possible
- Serve appropriately sized images to match the displayed dimensions

