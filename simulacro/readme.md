# 📚 Guía de HTML para el Examen - Conceptos Clave

✅ Estructura básica - DOCTYPE, html, head, body
✅ Etiquetas semánticas - header, nav, main, section, article, footer
✅ Jerarquía de títulos - h1 a h6
✅ Enlaces y navegación - atributos href, target, anclas
✅ Imágenes - src, alt, rutas relativas/absolutas
✅ Listas - ul, ol, li, listas anidadas
✅ Botones y formularios - button, input, label
✅ Contenedores - div vs span
✅ Atributos importantes - class, id, for
✅ Menú hamburguesa - técnica checkbox hack explicada paso a paso
✅ Estructura del proyecto - patrones de cada sección
✅ Buenas prácticas - indentación, atributos obligatorios
✅ Meta tags - viewport, charset, description
✅ Patrones comunes - hero, secciones, footer
✅ Consejos para el examen - checklist rápido
✅ Tabla de resumen - todas las etiquetas usadas

## 🎯 1. ESTRUCTURA BÁSICA DE UN DOCUMENTO HTML

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Título de la Página</title>
    <link rel="stylesheet" href="estilos.css">
</head>
<body>
    <!-- Contenido aquí -->
</body>
</html>
```

**¿Qué hace cada parte?**
- `<!DOCTYPE html>` - Declara que es un documento HTML5
- `<html lang="en">` - Elemento raíz, `lang` define el idioma
- `<head>` - Contiene metadatos (información invisible)
- `<meta charset="UTF-8">` - Codificación de caracteres (soporte para acentos)
- `<meta name="viewport">` - Hace la página responsive
- `<title>` - Título que aparece en la pestaña del navegador
- `<link rel="stylesheet">` - Conecta archivo CSS
- `<body>` - Contiene todo el contenido visible

---

## 🏗️ 2. ETIQUETAS SEMÁNTICAS (HTML5)

### ¿Qué son?
Etiquetas que describen el **significado** del contenido, no solo su apariencia.

```html
<header>    <!-- Encabezado de la página o sección -->
<nav>       <!-- Navegación principal -->
<main>      <!-- Contenido principal -->
<section>   <!-- Sección de contenido -->
<article>   <!-- Contenido independiente (blog post, noticia) -->
<aside>     <!-- Contenido lateral o relacionado -->
<footer>    <!-- Pie de página -->
<figure>    <!-- Contenido ilustrativo (imagen + descripción) -->
<figcaption> <!-- Descripción de una figura -->
```

### Ejemplo completo
```html
<header>
    <nav>
        <!-- Menú de navegación -->
    </nav>
</header>

<main>
    <section>
        <article>
            <!-- Contenido del artículo -->
        </article>
    </section>
</main>

<footer>
    <!-- Información del pie de página -->
</footer>
```

**¿Por qué son importantes?**
- Mejoran el SEO (buscadores entienden mejor tu página)
- Mejoran la accesibilidad (lectores de pantalla)
- Hacen el código más legible y mantenible

---

## 📝 3. JERARQUÍA DE TÍTULOS

```html
<h1>Título Principal</h1>        <!-- Solo UNO por página -->
<h2>Título de Sección</h2>       <!-- Subsecciones principales -->
<h3>Subtítulo</h3>               <!-- Subsecciones de h2 -->
<h4>Sub-subtítulo</h4>           <!-- Subsecciones de h3 -->
<h5>Título menor</h5>            <!-- Menos común -->
<h6>Título más pequeño</h6>      <!-- Menos común -->
```

**Reglas importantes:**
- Solo debe haber **UN** `<h1>` por página
- No saltes niveles (después de h2 va h3, no h4)
- Los títulos ayudan al SEO y accesibilidad
- En el proyecto: h1 → h2 → h3 → h4 → h5

---

## 🔗 4. ENLACES Y NAVEGACIÓN

### Enlace básico
```html
<a href="https://ejemplo.com">Texto del enlace</a>
```

### Enlace a sección de la misma página
```html
<a href="#seccion">Ir a sección</a>

<!-- Más abajo en la página -->
<section id="seccion">
    <!-- Contenido -->
</section>
```

### Enlace sin destino (placeholder)
```html
<a href="#">Enlace temporal</a>
```

### Atributos importantes
```html
<a href="url" target="_blank">Abre en nueva pestaña</a>
<a href="url" rel="noopener">Seguridad para target="_blank"</a>
<a href="mailto:correo@ejemplo.com">Enviar email</a>
<a href="tel:+123456789">Llamar por teléfono</a>
```

---

## 🖼️ 5. IMÁGENES

### Imagen básica
```html
<img src="ruta/imagen.jpg" alt="Descripción de la imagen">
```

### Atributos importantes
```html
<img 
    src="assets/img/logo.svg"        <!-- Ruta de la imagen -->
    alt="Logo de la empresa"         <!-- Texto alternativo (OBLIGATORIO) -->
    width="300"                      <!-- Ancho en píxeles -->
    height="200"                     <!-- Alto en píxeles -->
>
```

**¿Por qué el atributo `alt` es obligatorio?**
- Accesibilidad (lectores de pantalla)
- SEO (buscadores leen el texto)
- Se muestra si la imagen no carga
- Si es decorativa, usar `alt=""` (vacío)

### Tipos de rutas
```html
<!-- Ruta relativa -->
<img src="assets/img/logo.svg" alt="Logo">

<!-- Ruta absoluta -->
<img src="/assets/img/logo.svg" alt="Logo">

<!-- URL externa -->
<img src="https://ejemplo.com/imagen.jpg" alt="Imagen">
```

---

## 📋 6. LISTAS

### Lista desordenada (ul)
```html
<ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ul>
```

### Lista ordenada (ol)
```html
<ol>
    <li>Primer paso</li>
    <li>Segundo paso</li>
    <li>Tercer paso</li>
</ol>
```

### Listas anidadas
```html
<ul>
    <li>Item principal
        <ul>
            <li>Subitem 1</li>
            <li>Subitem 2</li>
        </ul>
    </li>
</ul>
```

**Uso en el proyecto:**
```html
<ul class="nav-menu">
    <li class="dropdown">
        <a href="#product">Product</a>
        <ul class="dropdown-menu">
            <li><a href="#overview">Overview</a></li>
            <li><a href="#pricing">Pricing</a></li>
        </ul>
    </li>
</ul>
```

---

## 🔘 7. BOTONES Y FORMULARIOS

### Botones
```html
<!-- Botón estándar -->
<button>Click aquí</button>

<!-- Botón con clase -->
<button class="btn-primary">Registrarse</button>

<!-- Botón tipo submit (envía formulario) -->
<button type="submit">Enviar</button>

<!-- Botón tipo button (no envía) -->
<button type="button">Hacer algo</button>
```

### Input (Checkbox para menú hamburguesa)
```html
<input type="checkbox" id="menu-toggle" class="menu-toggle">
```

**Tipos de input comunes:**
```html
<input type="text">       <!-- Texto -->
<input type="email">      <!-- Email -->
<input type="password">   <!-- Contraseña -->
<input type="number">     <!-- Número -->
<input type="checkbox">   <!-- Casilla de verificación -->
<input type="radio">      <!-- Botón de radio -->
<input type="file">       <!-- Subir archivo -->
<input type="submit">     <!-- Botón de envío -->
```

### Label (asociado con input)
```html
<label for="menu-toggle">Abrir menú</label>
<input type="checkbox" id="menu-toggle">
```

**¿Por qué usar label?**
- Al hacer click en el label, activa el input asociado
- Mejora la accesibilidad
- Útil para el menú hamburguesa (checkbox hack)

---

## 📦 8. CONTENEDORES (DIV y SPAN)

### DIV - Contenedor de bloque
```html
<div class="contenedor">
    <!-- Ocupa todo el ancho disponible -->
    <!-- Crea un salto de línea antes y después -->
</div>
```

### SPAN - Contenedor en línea
```html
<p>Este es un <span class="destacado">texto destacado</span> dentro de un párrafo.</p>
```

**Diferencias:**
- `<div>` = Bloque (ocupa toda la línea)
- `<span>` = En línea (solo ocupa su contenido)

---

## 🎯 9. ATRIBUTOS IMPORTANTES

### Class (para CSS)
```html
<div class="contenedor">Contenido</div>
<div class="contenedor principal">Múltiples clases</div>
```

### ID (único en la página)
```html
<div id="hero">Contenido único</div>
```

**Diferencias entre class e id:**
- **class**: Puede repetirse, se usa para estilos comunes
- **id**: Único, se usa para JavaScript o anclas
- En CSS: `.clase` vs `#id`

### Otros atributos comunes
```html
<img src="..." alt="...">           <!-- src, alt -->
<a href="..." target="...">         <!-- href, target -->
<input type="..." id="..." name="...">  <!-- type, id, name -->
<button disabled>No disponible</button>  <!-- disabled -->
```

---

## 🍔 10. MENÚ HAMBURGUESA (Checkbox Hack)

### Estructura completa
```html
<!-- 1. Checkbox oculto (controla el estado abierto/cerrado) -->
<input type="checkbox" id="menu-toggle" class="menu-toggle">

<!-- 2. Label que actúa como botón (al hacer click, activa el checkbox) -->
<label for="menu-toggle" class="hamburger">
    <span class="hamburger-icon"></span>
</label>

<!-- 3. Menú que se muestra/oculta según el estado del checkbox -->
<ul class="nav-menu">
    <li><a href="#">Inicio</a></li>
    <li><a href="#">Servicios</a></li>
    <li><a href="#">Contacto</a></li>
</ul>
```

### CSS asociado (recordatorio)
```css
/* Ocultar checkbox */
.menu-toggle {
    display: none;
}

/* Menú oculto por defecto */
.nav-menu {
    right: -100%;
    transition: right 0.3s;
}

/* Mostrar menú cuando checkbox está checked */
.menu-toggle:checked ~ .nav-menu {
    right: 0;
}
```

**¿Cómo funciona?**
1. El usuario hace click en el `<label>`
2. Esto activa/desactiva el `<input type="checkbox">`
3. CSS detecta el estado `:checked`
4. Cambia los estilos del menú (visible/oculto)

---

## 🎨 11. ESTRUCTURA DEL PROYECTO BLOGR

### Header (Encabezado)
```html
<header>
    <nav class="nav">
        <!-- Logo -->
        <div class="logo">
            <img src="..." alt="Logo">
        </div>
        
        <!-- Checkbox y hamburguesa -->
        <input type="checkbox" id="menu-toggle" class="menu-toggle">
        <label for="menu-toggle" class="hamburger">
            <span class="hamburger-icon"></span>
        </label>
        
        <!-- Menú de navegación -->
        <ul class="nav-menu">
            <!-- Items del menú -->
        </ul>
        
        <!-- Botones de login -->
        <div class="nav-login">
            <button class="btn-login">Login</button>
            <button class="btn-signup">Sign Up</button>
        </div>
    </nav>
    
    <!-- Hero -->
    <div class="hero">
        <div class="hero-content">
            <h1>Título Principal</h1>
            <p>Descripción</p>
            <div class="hero-buttons">
                <button class="btn-star">Start for Free</button>
                <button class="btn-learn">Learn More</button>
            </div>
        </div>
    </div>
</header>
```

### Main (Contenido Principal)
```html
<main>
    <!-- Sección 1 -->
    <section class="description-section">
        <h2>Título de Sección</h2>
        
        <div class="content-row">
            <!-- Columna de texto -->
            <div class="text-column">
                <article class="description-content">
                    <h3>Subtítulo</h3>
                    <p>Descripción...</p>
                </article>
            </div>
            
            <!-- Columna de imagen -->
            <div class="img">
                <div class="img-1">
                    <img src="..." alt="...">
                </div>
            </div>
        </div>
    </section>
    
    <!-- Más secciones... -->
</main>
```

### Footer (Pie de página)
```html
<footer>
    <div class="footer-content">
        <!-- Logo -->
        <div class="logo">
            <img src="..." alt="Logo">
        </div>
        
        <!-- Columnas de enlaces -->
        <div class="footer-column">
            <h6>Título</h6>
            <ul>
                <li><a href="#">Enlace 1</a></li>
                <li><a href="#">Enlace 2</a></li>
            </ul>
        </div>
        
        <!-- Más columnas... -->
    </div>
</footer>
```

---

## 💡 12. BUENAS PRÁCTICAS HTML

### 1. Indentación correcta
```html
<!-- ✅ BIEN -->
<div class="contenedor">
    <h1>Título</h1>
    <p>Párrafo</p>
</div>

<!-- ❌ MAL -->
<div class="contenedor">
<h1>Título</h1>
<p>Párrafo</p>
</div>
```

### 2. Cerrar todas las etiquetas
```html
<!-- ✅ BIEN -->
<div>Contenido</div>
<img src="..." alt="...">  <!-- Las auto-cerradas no necesitan / al final en HTML5 -->

<!-- ❌ MAL -->
<div>Contenido
<img src="..." alt="..."></img>
```

### 3. Usar minúsculas
```html
<!-- ✅ BIEN -->
<div class="contenedor">

<!-- ❌ MAL (aunque funciona) -->
<DIV CLASS="contenedor">
```

### 4. Comillas en atributos
```html
<!-- ✅ BIEN -->
<img src="imagen.jpg" alt="Descripción">

<!-- ❌ MAL -->
<img src=imagen.jpg alt=Descripción>
```

### 5. Atributo alt obligatorio en imágenes
```html
<!-- ✅ BIEN -->
<img src="logo.svg" alt="Logo de la empresa">
<img src="decoracion.svg" alt="">  <!-- Si es decorativa -->

<!-- ❌ MAL -->
<img src="logo.svg">
```

---

## 🎯 13. ELEMENTOS DE TEXTO

### Párrafos y saltos de línea
```html
<p>Este es un párrafo.</p>
<p>Este es otro párrafo.</p>

<p>Primera línea<br>Segunda línea</p>  <!-- <br> salto de línea -->
```

### Énfasis y strong
```html
<em>Texto en cursiva (énfasis)</em>
<strong>Texto en negrita (importancia)</strong>

<!-- Evitar usar solo para estilo -->
<i>Cursiva visual</i>
<b>Negrita visual</b>
```

### Citas y código
```html
<blockquote>Esto es una cita en bloque</blockquote>
<q>Cita corta en línea</q>
<code>let x = 5;</code>  <!-- Código en línea -->
<pre>
    Texto
    preformateado
</pre>
```

---

## 📱 14. META TAGS IMPORTANTES

```html
<head>
    <!-- Codificación de caracteres -->
    <meta charset="UTF-8">
    
    <!-- Viewport para responsive -->
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    
    <!-- Descripción para SEO -->
    <meta name="description" content="Descripción de la página">
    
    <!-- Palabras clave (menos importante hoy en día) -->
    <meta name="keywords" content="html, css, web">
    
    <!-- Autor -->
    <meta name="author" content="Tu Nombre">
</head>
```

---

## 🔗 15. NAVEGACIÓN CON DROPDOWN

```html
<nav class="nav">
    <ul class="nav-menu">
        <!-- Item simple -->
        <li>
            <a href="#inicio">Inicio</a>
        </li>
        
        <!-- Item con dropdown -->
        <li class="dropdown">
            <a href="#servicios">
                Servicios
                <img src="arrow.svg" alt="">
            </a>
            <!-- Submenú -->
            <ul class="dropdown-menu">
                <li><a href="#web">Desarrollo Web</a></li>
                <li><a href="#app">Apps Móviles</a></li>
                <li><a href="#seo">SEO</a></li>
            </ul>
        </li>
    </ul>
</nav>
```

---

## 📦 16. PATRONES COMUNES DEL PROYECTO

### Patrón: Sección con texto e imagen
```html
<section class="seccion">
    <h2>Título de Sección</h2>
    
    <div class="contenedor-grid">
        <!-- Texto a la izquierda -->
        <div class="columna-texto">
            <article>
                <h3>Subtítulo</h3>
                <p>Descripción del contenido...</p>
            </article>
        </div>
        
        <!-- Imagen a la derecha -->
        <div class="columna-imagen">
            <img src="imagen.jpg" alt="Descripción">
        </div>
    </div>
</section>
```

### Patrón: Hero con botones
```html
<div class="hero">
    <div class="hero-content">
        <h1>Título Grande</h1>
        <p>Descripción breve</p>
        
        <div class="botones">
            <button class="btn-primario">Acción Principal</button>
            <button class="btn-secundario">Acción Secundaria</button>
        </div>
    </div>
</div>
```

### Patrón: Footer con columnas
```html
<footer>
    <div class="footer-grid">
        <!-- Logo -->
        <div class="logo">
            <img src="logo.svg" alt="Logo">
        </div>
        
        <!-- Columna 1 -->
        <div class="columna">
            <h6>Producto</h6>
            <ul>
                <li><a href="#">Features</a></li>
                <li><a href="#">Pricing</a></li>
            </ul>
        </div>
        
        <!-- Columna 2 -->
        <div class="columna">
            <h6>Empresa</h6>
            <ul>
                <li><a href="#">About</a></li>
                <li><a href="#">Contact</a></li>
            </ul>
        </div>
    </div>
</footer>
```

---

## 🎓 CONSEJOS PARA EL EXAMEN

### ✅ Estructura correcta
1. Siempre empieza con `<!DOCTYPE html>`
2. Incluye `<html>`, `<head>` y `<body>`
3. Usa etiquetas semánticas (`<header>`, `<nav>`, `<main>`, `<footer>`)
4. Solo un `<h1>` por página

### ✅ Atributos esenciales
1. `alt` en todas las imágenes
2. `href` en todos los enlaces
3. `class` para CSS
4. `id` para elementos únicos
5. `for` en labels (conecta con input)

### ✅ Jerarquía
1. Header → Nav → Main → Footer
2. Section → Article → H2/H3 → P
3. No saltar niveles de títulos (h1 → h2 → h3)

### ✅ Menú hamburguesa
1. Input checkbox oculto con `display: none`
2. Label con `for="id-del-checkbox"`
3. CSS usa selector `:checked` para mostrar/ocultar

### ✅ Listas de navegación
1. Usa `<ul>` y `<li>` para menús
2. Anida listas para dropdowns
3. Usa clases descriptivas

### ✅ Responsive
1. Meta viewport en el `<head>`
2. No uses width fijos en píxeles
3. Usa unidades relativas (rem, %, vh, vw)

---

## 🚀 CHECKLIST RÁPIDO

```
☐ <!DOCTYPE html> al inicio
☐ <html lang="es">
☐ <meta charset="UTF-8">
☐ <meta name="viewport" content="...">
☐ <title> con nombre apropiado
☐ <link rel="stylesheet" href="...">
☐ Solo UN <h1> por página
☐ alt en TODAS las imágenes
☐ Etiquetas semánticas (header, nav, main, footer)
☐ Indentación correcta
☐ Todas las etiquetas cerradas
☐ Estructura lógica y ordenada
```

---

## 📝 RESUMEN DE ETIQUETAS DEL PROYECTO

| Etiqueta | Uso en el proyecto |
|----------|-------------------|
| `<header>` | Encabezado con gradiente |
| `<nav>` | Barra de navegación |
| `<ul>`, `<li>` | Menús y listas |
| `<a>` | Enlaces del menú y footer |
| `<img>` | Logo e ilustraciones |
| `<button>` | Botones de login y CTA |
| `<input>` | Checkbox para menú móvil |
| `<label>` | Activa el checkbox |
| `<div>` | Contenedores para layout |
| `<h1>`-`<h6>` | Títulos jerárquicos |
| `<p>` | Párrafos de texto |
| `<section>` | Secciones de contenido |
| `<article>` | Contenido independiente |
| `<main>` | Contenido principal |
| `<footer>` | Pie de página |

---

¡Estudia estos conceptos y estarás perfectamente preparado para tu examen de HTML! 🎓💪