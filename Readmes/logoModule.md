# Modulo de Logo
```css
.logo {
  overflow: hidden;
  display: inline-block;
}
.logo-primary {
  width: 64px;
  height: 64px;
}
.logo-primary img {
  height: 100%;
}

@media only screen and (min-width : 48em) { /* para pantallas grandes se organiza a el lado derecho de la pantalla */
    .logo-primary{
        width: auto;
        height: 50px;
        margin-right: auto;
    }
}
```

```html
<a class="logo logo-primary">
    <img src="images/logo.png">
</a>
```