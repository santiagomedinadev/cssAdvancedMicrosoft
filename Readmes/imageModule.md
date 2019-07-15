# Modulo de imagen
```css
.bg-image  {
  width: 100%;
  overflow: hidden;
  position: relative;
}
.bg-image > img {
  position: absolute;
  top: -9999px;
  bottom: -9999px;
  left: -9999px;
  right: -9999px;
  margin: auto;
}
```

```html
<section class="hero hero-primary bg-image">
    <img src="images/hero.jpg">
    <div class="container">
        <div class="hero-body">
            <h1 class="hero-title">Hero Primary Title Content</h1>
            <h4 class="hero-subtitle">Hero Primary Subtitle Content</h4>
            <button class="btn btn-secondary">Button Text</button>
        </div>
    </div>
</section>
```