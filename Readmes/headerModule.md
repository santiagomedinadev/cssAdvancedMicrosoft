# Modulo de Header

```css
.header-primary {
  background: #9B8579;
  text-align: center;
  padding-top: 18px;
  padding-bottom: 18px;
}
@media only screen and (min-width : 48em) { /* para pantallas grande se quita el background y se pone por encima de los demas elementos*/
    .header-primary{
        background: none;
        position: absolute;
        z-index: 99;
        width: 100%;
    }
    .header-primary:after{
        content: "";
        display: table;
        clear: both;
    }
}
```

```html
<header class="header-primary">
```