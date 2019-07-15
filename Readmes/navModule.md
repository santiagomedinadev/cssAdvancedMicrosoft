# Modulo de Nav

```css
.nav > ul {
  list-style: none;
  padding: 0px;
  margin: 0px;
}
.nav-primary {
  margin-top: 28px;
}

@media only screen and (min-width : 48em) { /* para pantallas grandes se organizan todas en una fila*/
    .nav-primary {
        margin-top: 0px;
    }
    .nav-primary li {
        display: inline-block;
    }
}
```

```html
<nav class="nav nav-primary">
    <ul>
        <li><a href="#" class="btn btn-nav">Link</a></li>
        <li><a href="#" class="btn btn-nav">Link</a></li>
        <li><a href="#" class="btn btn-nav">Link</a></li>
        <li><a href="#" class="btn btn-primary">Link</a></li>
    </ul>
</nav>
```