# Portafolio - Sergio Cortes

- **Nombre:** Sergio Alejandro Cortes Galindo
- **Clan:** Hopper
- **Correo:** contacto.sergiocortes@gmail.com
- **Documento Identidad:** 1027524163

---

## Estructura

```
│── assets/
│───── imgs/
│───────  aodesu.png/
│───────  benkyo.png/
│───────  new_portfolio.png/
│───────  old_portfolio.png/
│── index.html
│── contact.html
│── projects.html
│── styles.css
│── README.md
```

## Elementos principales

Cada página tiene un `<header>`, `<main>` y un `<footer>`

### `<header>`

Esta fijo en la parte superior de la pantalla (parte inferior en moviles).
Contiene el menu de navegación que tiene 3 enlaces. Los enlaces redirigen al inicio (`index.html`), los proyectos (`projects.html`) y el contáctame (`contact.html`).

### `<main>`

La etiqueta main contiene varias secciones (`<section>`), cada sección tiene un encabezado (`<h1>`...`<h3>`) y algunos tienen párrafos (`<p>`).

#### `<section>`

Section engloba todo el contenido respecto a una categoría. Tienen un elemento flotante al final de ellos para una navegación mas cómoda entre secciones.

### `<footer>`

El footer contiene:
- Mi nombre
- Mis redes sociales
- Marca de copyright

## CSS

El css tiene unos comentarios que indican jerarquía.

- Comentario con muchos "==="
    - Comentario con dos "**" al inicio y al final. Todas mayúsculas.
        - Comentario con un "*" al inicio y al final. Todas minúsculas.

Antes de esos comentarios están los estilos globales. Son clases y variables que se reutilizan a lo largo de toda la página.

No se necesitaron más de 2 media query (768px) y (544px).