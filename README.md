# Guia de CSS Avanzado
Esta guia sirve para realizar un mejor css con buenas practicas de programación.

## ¿Qué es un sitio web responsivo?
Es una manera de crear vistas flexibles y optimas para una variedad de diferentes dispositivos.

## ¿Comó trabaja una media query con CSS para adaptar nuestras vistas?
Una media query permite acoplar cierto CSS basado en el dispositivo del usuario y la query del dispositivo o navegador, permitiendo cargar CSS apropiadamente.
```css
@media screen and (min-width:768px){
    //code
}
```

## Breakpoints de dispositivos
```css
/* celulares */
@media screen and (max-width:767px){...}

/* tablets */
@media (min-width:768px) and (max-width:991px){...}

/* tablets - desktops */
@media (min-width:992px) and (max-width:1199px){...}

/* desktops */
@media screen and (min-width:1200px){...}
```
### Nota
Para dispositivos con pantallas muy grandes, es mejor limitar el ancho maximo del contenedor para que no consuma toda la pantalla:
```css
.container {
    max-width: 62.5rem;
}
```

## Trabajando con imagenes
Las imagenes pueden consumir muchos recursos, por lo que es importante seleccionar con cuidado el numero de imagenes y su tamaño al momento de diseñar una pagina web, ademas de tener en cuenta los siguientes puntos:
- Las imagenes deben tener una resolución adecuada para su uso en web
- Grabar las imagenes en los formatos: JPEG(mejor para web), PNG o GIF
- Incluir el atributo "alt", esto ayuda a el SEO de la pagina, tambien permite que los ciego puedan saber que hay en la pagina web por medio de programas de lectura de pantalla y si la imagen no carga muestra de que se trata dicha imagen.

```css
/* hacer una imagen responsive */
img{
    max-width:100%;
    height:auto;
}
```

## Normalización
Es una forma para que todos los diferentes navegadores web tengan consistencia en sus estilos por defecto de los elementos HTML.
- Archivo [normalize.css](http://nicolasgallagher.com/about-normalize-css/).
```css
@import 'normalize.css';
html{
    box-sizing: border-box;
}
*, *:before, *:after{
    box-sizing: inherit;
}
```
Aparte del archivo de normalización, estos permite que cuando uno fija un ancho y alto de un elemento este no se vea afectado por sus elementos internos o sus propiedades como padding, para mayor información mirar el [enlace](http://www.paulirish.com/2012/box-sizing-border-box-ftw/).

## Construir un CSS base
Es importante mantener tu base simple para que no asumas estilos que despues necesitaras sobreescribir.
```css
body { 
    color: #414042;
    font-family: Arial, Helvetica, sans-serif;
    font-weight: normal;
}

h1, h2, h3 {
    font-weight:bold;
}

a {
    color: #8dc63f;
    font-weight:bold;
}

a:hover {
    text-decoration: underline;
}
```

## Crear un sistema basico de grillas
```css
.container {
    padding-right: 15px;
    padding-left: 15px;
    margin-right: auto;
    margin-left: auto;
    max-width: 1170px;
} /* 15px + 15px + 1170px = 1200px */

.row{
    margin-right: -15px;
    margin-left: -15px;
} /* para que quede a ras con el .container */

.row:after {
    content: "";
    display: tablet;
    clear: both;
} /* para que todo elemento flotante permanezca adentro del .row */
```
mas información en el [enlace](https://www.sitepoint.com/clearing-floats-overview-different-clearfix-methods/).

### Crear columnas
siguiendo la regla del diseño responsive "mobile first", vamos a crear nuestras columnas para moviles y por medio de media queries modificaremos para tamaños mas grandes:
```css
[class*='col-'] {
    width: 100%;
    padding-left: 15px;
    padding-right: 15px;
}

@media only screen and (max-width: 47.9375em) { /* 48em - 1px = 47.9375em */
    .remove-gutter-xs {
        padding-left: 0px;
        padding-right: 0px;
    }
}

/* media query para tamaños mas grandes */
@media (min-width: 48em) {
    [class*='col-'] {
        float: left;
    }

    .col-1-3 {
        width: 33.3333%;
    }

    .col-2-3 {
        width: 66.6666%;
    }

    .col-1-2 {
        width: 50%;
    }
}

@media (min-width: 48em) {
    .pull-right-sm {
        float: right;
    }
}
```

```html
<body>
    <header>
        <div class="container">
            -----------
        </div>
    </header>

    <main>
        <section>
            <div class="container">
                -------------
            </div>
        </section>
    </main>
</body>
```

```html
<section>
    <div class="container">
        <div class="row">
            <div class="col-1-3">
                Circle Image
            </div>
            <div class="col-2-3">
                Content Area
            </div>
        </div>
    </div>
</section>
```

## Has tu CSS Modular
El término "Módulo" se usa a menudo en el desarrollo para describir un bloque de construcción encapsulado que forma parte de un programa más grande. En el contexto de CSS, Modular CSS describe un enfoque coherente para crear CSS que se divide en partes más pequeñas.

```css
/* NO ES MODULAR */
.content-area .btn{
    //code
}

/* SI ES MODULAR */
.btn { 
    padding: .5em 1em; 
    text-decoration: none; 
    border: 1px gray solid; 
    display: inline-block //helps anchors and other inline elements 
} 

.btn—content {
    background: blue;
    color: white;
}
```

```html
<i class="fa fa-thumbs-up fa-4x fa-spin"></i>
```

### Guias para modularizar
- OOCSS [http://oocss.org/](http://oocss.org/)
- SMACSS [https://smacss.com/](https://smacss.com/)
- BEM [http://getbem.com/](http://getbem.com/)

## Posicionamiento avanzado con css
```css
.logo {
    display: inline-block;
    font-family: georgia;
    float: left;
}

.pull-left {
    float: left;
}

.pull-right {
    float: right;
}
```

```html
<header>
    <div class="pull-left">
        <div class="logo">Logo</div>
    </div>
</header>
```

## Abstrayendo posicionamiento
- La posicion "relative" es practicamente estaticas hasta que una propiedad es aplicada. Utilizando "top", "left", "right" y "bottom" es posible mover el elemento de forma relativa a su posicion original. Los otros modulos respetan la posicion original del elemento, es por esto que aunque el elemento se mueva de posicion los otros elementos no se van a reorganizar.

- La posicion "absolute" desplaza al elemento a el borde superior izquierdo del primer elemento padre que lo contenga y que posea posicion ya sea "relative" o "absolute".

- Usa la propiedad "z-index" para apilar modulos absolutos sobre otros modulos relativos y absolutos.

```html
<!—Model HTML—>
<div class=“model”>
    <div class=“modal-header”>
        <h5 class=“modal-header__title”>Hello World</h5>
        <div class=“modal-header__btn-wrap”>
            <button class="btn"><i class=“fa fa-close“></i> close</button>
        </div>
    </div>

    <div class=“modal-body”>…</div>
    <div class=“modal-footer”>…</div>
</div>
```

```css
.modal-header__btn-wrap {
   position: absolute;
   top: 0.75rem;
   right: 0.75rem;
}

.modal-header {
   position: relative; //este es el contenedor para modal-header__btn-wrap
}
```