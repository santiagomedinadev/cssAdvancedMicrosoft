# Modulo de Boton
- convertir px a em -> [enlace](http://pxtoem.com/).
- transiciones de estilos -> [enlace](http://www.w3schools.com/css/css3_transitions.asp).

```css
/*Button Modules*/
.btn {
  display: inline-block;
  text-align: center;
  white-space: nowrap;
  vertical-align: middle;
  background-image: none;
  border: 1px solid transparent; /* el color del border va a ser modificado por otras clases asi que por defecto se pone transparante en caso de que sea el btn base */
  cursor: pointer;
  text-decoration: none;
  padding: 12px 30px;
  font-size: 1.313em;
  font-weight: bold;
  border-radius: 4px;
  transition: all 0.3s ease 0s; /* incluye una transicion */
}

.btn-primary {
  background: #8DC63F;
  border-color: #8DC63F;
  color: white;
}

.btn-primary:hover {
  background: none;
  border-color: white;
  text-decoration: none;
}

.btn-nav {
  color: white;
}
```