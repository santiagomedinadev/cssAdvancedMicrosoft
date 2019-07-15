# Modulo de Hero
```css
.hero {
  text-align: center;
}
.hero-primary {
  background-color: #594a42;
  color: white;
  padding-top: 25px;
  padding-bottom: 25px;
}
.hero-primary.bg-image > img {
  opacity: 0.55;
}
.hero-body {
  position: relative; /* para estar en frente de la imagen de background */
}
.hero-title {
  margin-top: 25px;
  margin-bottom: 25px;
  font-size: 2.625em;
}
.hero-subtitle {
  margin-top: 25px;
  margin-bottom: 25px;
  font-size: 1.500em;
  font-weight: normal;
}
.hero-subtitle + button {
  margin-top: 25px;
}

@media only screen and (min-width : 48em) { /* para pantallas grandes se coloca un padding grande para darle espacio a el navbar */
    .hero-primary {
        padding-top: 150px;
    }
}
```

```html
<section class="hero hero-primary">
    <div class="container">
        <div class="hero-body">
            <h1 class="hero-title">Hero Primary Title Content</h1>
            <h4 class="hero-subtitle">Hero Primary Subtitle Content</h4>
            <button class="btn btn-secondary">Button Text</button>
        </div>
    </div>
</section>
```