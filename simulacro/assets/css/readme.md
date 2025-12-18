El CSS está organizado en estas secciones principales:

RESET Y BASE - Estilos iniciales y configuración básica
NAVEGACIÓN - Menú principal con hamburguesa para móvil
HEADER - Sección hero con gradiente
SECCIONES - Contenido principal con imágenes y texto
SECCIÓN AZUL - Bloque con fondo oscuro y pattern
FOOTER - Pie de página
RESPONSIVE - Media queries para diferentes tamaños de pantalla:

Laptops pequeños (≤1024px)
Tablets (≤768px)
Móviles grandes (≤640px)
Móviles pequeños (≤480px)

----------------------------------------------------------------------------------------------------------

# 📚 Guía de CSS para el Examen - Conceptos Clave

✅ Conceptos fundamentales: Reset, Flexbox, Grid, Posicionamiento
✅ Efectos visuales: Transiciones, animaciones, gradientes, sombras
✅ Técnicas avanzadas: Menú hamburguesa, dropdowns, responsive design
✅ Selectores CSS: Todos los tipos que necesitas conocer
✅ Unidades y medidas: px, rem, %, vh, vw
✅ Trucos útiles: Centrado, truncado de texto, aspect ratio
✅ Consejos para el examen: Tips importantes para recordar
✅ Patrones comunes: Ejemplos prácticos del proyecto

## 🎯 1. RESET Y BOX-SIZING

```css
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}
```
**¿Para qué sirve?**
- Elimina márgenes y padding por defecto del navegador
- `box-sizing: border-box` hace que width/height incluyan padding y border

---

## 📐 2. FLEXBOX - Alineación y Distribución

### Contenedor Flex Básico
```css
.contenedor {
    display: flex;
    align-items: center;      /* Centrado vertical */
    justify-content: center;  /* Centrado horizontal */
    gap: 2rem;               /* Espacio entre elementos */
}
```

### Dirección de Flex
```css
.vertical {
    flex-direction: column;  /* Apila verticalmente */
}

.horizontal {
    flex-direction: row;     /* Alinea horizontalmente (default) */
}
```

### Flex en elementos hijos
```css
.elemento-hijo {
    flex: 1;  /* Ocupa todo el espacio disponible */
}

.empujar-derecha {
    margin-left: auto;  /* Empuja elemento a la derecha */
}
```

---

## 🎨 3. CSS GRID - Layouts en Cuadrícula

### Grid de 2 columnas iguales
```css
.grid-container {
    display: grid;
    grid-template-columns: 1fr 1fr;  /* 2 columnas iguales */
    gap: 2rem;
    align-items: center;
}
```

### Grid de 4 columnas
```css
.grid-4-columnas {
    display: grid;
    grid-template-columns: repeat(4, 1fr);  /* 4 columnas iguales */
    gap: 4rem;
}
```

### Grid responsive
```css
@media (max-width: 768px) {
    .grid-container {
        grid-template-columns: 1fr;  /* 1 columna en móvil */
    }
}
```

---

## 🎭 4. POSICIONAMIENTO

### Position Relative
```css
.padre {
    position: relative;  /* Crea contexto para hijos absolutos */
}
```

### Position Absolute
```css
.hijo-absoluto {
    position: absolute;
    top: 100%;     /* Debajo del padre */
    left: 0;       /* Alineado a la izquierda */
}
```

### Position Fixed
```css
.menu-fijo {
    position: fixed;
    top: 0;
    right: -100%;  /* Oculto fuera de pantalla */
    width: 280px;
    height: 100vh;
    transition: right 0.3s ease;
}

.menu-fijo.abierto {
    right: 0;  /* Visible */
}
```

---

## ✨ 5. TRANSICIONES Y ANIMACIONES

### Transiciones básicas
```css
.elemento {
    transition: all 0.3s ease;  /* Anima todas las propiedades */
}

.boton {
    transition: background 0.3s, color 0.3s;  /* Propiedades específicas */
}
```

### Transforms
```css
.rotar {
    transform: rotate(45deg);
}

.mover {
    transform: translateY(-10px);  /* Mueve hacia arriba */
}

.escalar {
    transform: scale(1.1);  /* Agranda 110% */
}
```

---

## 🎨 6. BACKGROUNDS Y GRADIENTES

### Gradiente lineal
```css
.gradiente {
    background: linear-gradient(135deg, #ff8f70, #ff3d54);
}
```

### Background con imagen
```css
.fondo-con-imagen {
    background: #3b3c59 url(../img/pattern.svg) no-repeat left -10rem top -33rem;
}
```

---

## 🔲 7. BORDES Y SOMBRAS

### Border radius
```css
.redondeado {
    border-radius: 8px;  /* Esquinas redondeadas */
}

.esquina-especifica {
    border-bottom-left-radius: 100px;  /* Solo una esquina */
    border-top-right-radius: 100px;
}

.pildora {
    border-radius: 30px;  /* Forma de píldora */
}
```

### Box Shadow
```css
.sombra {
    box-shadow: 0 8px 20px rgba(0, 0, 0, 0.15);
    /* x-offset, y-offset, blur, color */
}
```

---

## 👁️ 8. VISIBILIDAD Y OPACIDAD

```css
.oculto {
    display: none;           /* Oculto completamente */
}

.invisible {
    opacity: 0;              /* Invisible pero ocupa espacio */
    visibility: hidden;       /* No visible ni clickeable */
}

.semi-transparente {
    opacity: 0.8;            /* 80% visible */
}
```

---

## 🍔 9. MENÚ HAMBURGUESA (Checkbox Hack)

### HTML necesario
```html
<input type="checkbox" id="menu-toggle" class="menu-toggle">
<label for="menu-toggle" class="hamburger">
    <span class="hamburger-icon"></span>
</label>
<ul class="nav-menu">...</ul>
```

### CSS del hamburguesa
```css
.menu-toggle {
    display: none;  /* Oculta el checkbox */
}

.hamburger-icon {
    width: 30px;
    height: 3px;
    background-color: white;
    position: relative;
    transition: all 0.3s ease;
}

/* Líneas superior e inferior */
.hamburger-icon::before,
.hamburger-icon::after {
    content: '';
    position: absolute;
    width: 30px;
    height: 3px;
    background-color: white;
    transition: all 0.3s ease;
}

.hamburger-icon::before { top: -8px; }
.hamburger-icon::after { top: 8px; }

/* Animación a X cuando está activo */
.menu-toggle:checked ~ .hamburger .hamburger-icon {
    background-color: transparent;
}

.menu-toggle:checked ~ .hamburger .hamburger-icon::before {
    transform: rotate(45deg);
    top: 0;
}

.menu-toggle:checked ~ .hamburger .hamburger-icon::after {
    transform: rotate(-45deg);
    top: 0;
}

/* Mostrar menú cuando checkbox está checked */
.menu-toggle:checked ~ .nav-menu {
    right: 0;
}
```

---

## 🎯 10. DROPDOWN MENU (Hover)

```css
.dropdown {
    position: relative;
}

.dropdown-menu {
    position: absolute;
    top: 100%;
    left: 0;
    opacity: 0;
    visibility: hidden;
    transform: translateY(-10px);
    transition: all 0.3s;
}

.dropdown:hover .dropdown-menu {
    opacity: 1;
    visibility: visible;
    transform: translateY(0);
}
```

---

## 📱 11. MEDIA QUERIES - Responsive Design

### Breakpoints comunes
```css
/* Laptops pequeños */
@media (max-width: 1024px) {
    .contenedor { padding: 2rem; }
}

/* Tablets */
@media (max-width: 768px) {
    .grid { grid-template-columns: 1fr; }
}

/* Móviles grandes */
@media (max-width: 640px) {
    .hamburger { display: flex; }
}

/* Móviles pequeños */
@media (max-width: 480px) {
    h1 { font-size: 1.8rem; }
}
```

---

## 🎨 12. PSEUDO-ELEMENTOS

```css
.elemento::before {
    content: '';           /* Obligatorio para que aparezca */
    position: absolute;
    width: 100%;
    height: 100%;
}

.elemento::after {
    content: 'Texto adicional';
}
```

---

## 🖱️ 13. ESTADOS HOVER Y ACTIVE

```css
.boton {
    background: white;
    color: #ff8f70;
    transition: all 0.3s;
}

.boton:hover {
    background: #000;
    color: #fff;
    transform: scale(1.05);  /* Crece ligeramente */
}

.enlace:hover {
    opacity: 0.8;
    padding-left: 0.5rem;  /* Efecto de desplazamiento */
}
```

---

## 📏 14. UNIDADES CSS

```css
/* Unidades absolutas */
px    /* Píxeles - fijo */

/* Unidades relativas */
rem   /* Relativo al font-size del root (html) */
em    /* Relativo al font-size del padre */
%     /* Porcentaje del contenedor padre */
vh    /* Viewport height - 100vh = altura completa */
vw    /* Viewport width - 100vw = ancho completo */

/* Ejemplos */
.ejemplo {
    width: 100%;        /* 100% del padre */
    height: 100vh;      /* 100% de la pantalla */
    font-size: 1.2rem;  /* 1.2 veces el tamaño base */
    padding: 2em;       /* 2 veces el tamaño de fuente actual */
}
```

---

## 🎭 15. Z-INDEX (Capas)

```css
.capa-fondo {
    z-index: 1;
}

.capa-contenido {
    z-index: 100;
}

.capa-menu {
    z-index: 1000;
}

.capa-hamburguesa {
    z-index: 1001;  /* Sobre el menú */
}
```

---

## 🎨 16. COLORES Y OPACIDAD

```css
/* Formatos de color */
.colores {
    color: #ff8f70;                    /* Hexadecimal */
    color: rgb(255, 143, 112);         /* RGB */
    color: rgba(255, 143, 112, 0.5);   /* RGBA con transparencia */
}

/* Transparencia */
.transparente {
    background: rgba(0, 0, 0, 0.5);  /* Negro 50% transparente */
}
```

---

## 🔄 17. OVERFLOW

```css
.sin-scroll-horizontal {
    overflow-x: hidden;  /* Oculta scroll horizontal */
}

.con-scroll-vertical {
    overflow-y: auto;    /* Scroll vertical cuando sea necesario */
}

.sin-scroll {
    overflow: hidden;    /* Sin scroll en ninguna dirección */
}
```

---

## 📝 18. TIPOGRAFÍA

```css
.texto {
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1.2rem;
    font-weight: 700;      /* Negrita (100-900) */
    line-height: 1.8;      /* Altura de línea (espaciado) */
    text-align: center;    /* Alineación del texto */
    text-decoration: none; /* Sin subrayado */
}
```

---

## 🎯 19. CALC() - Cálculos en CSS

```css
.calculado {
    width: calc(100vw - 280px);     /* Viewport menos menú */
    height: calc(100% - 2rem);      /* 100% menos padding */
    margin: calc(2rem + 10px);      /* Suma de unidades */
}
```

---

## 🔧 20. TRUCOS Y TÉCNICAS ÚTILES

### Centrar elemento absoluto
```css
.centrado-absoluto {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
}
```

### Ocultar elemento visualmente pero accesible
```css
.sr-only {
    position: absolute;
    width: 1px;
    height: 1px;
    overflow: hidden;
    clip: rect(0, 0, 0, 0);
}
```

### Aspecto ratio
```css
.cuadrado {
    aspect-ratio: 1 / 1;  /* Siempre cuadrado */
}

.video {
    aspect-ratio: 16 / 9;  /* Formato video */
}
```

### Truncar texto
```css
.texto-truncado {
    white-space: nowrap;      /* No permite saltos de línea */
    overflow: hidden;         /* Oculta el exceso */
    text-overflow: ellipsis;  /* Muestra "..." */
}
```

---

## ⚡ 21. SELECTORES IMPORTANTES

```css
/* Selector universal */
* { }

/* Selector de clase */
.clase { }

/* Selector de ID */
#id { }

/* Selector de elemento */
div { }

/* Selector descendiente */
.padre .hijo { }

/* Selector hijo directo */
.padre > .hijo-directo { }

/* Selector hermano adyacente */
.elemento + .siguiente { }

/* Selector hermano general */
.elemento ~ .hermano { }

/* Pseudo-clase */
.elemento:hover { }
.elemento:first-child { }
.elemento:last-child { }
.elemento:nth-child(2) { }

/* Pseudo-elemento */
.elemento::before { }
.elemento::after { }

/* Selector de atributo */
input[type="checkbox"] { }

/* Selector combinado (checkbox checked + menú) */
.menu-toggle:checked ~ .nav-menu { }
```

---

## 💡 CONSEJOS PARA EL EXAMEN

1. **Flexbox** es ideal para layouts en una dimensión (fila o columna)
2. **Grid** es mejor para layouts en dos dimensiones (filas Y columnas)
3. **Position absolute** requiere un padre con `position: relative`
4. **Transitions** necesitan un estado inicial y uno final (hover, active, etc)
5. **Media queries** van de mayor a menor para mobile-first, o de menor a mayor para desktop-first
6. **Z-index** solo funciona con elementos posicionados (relative, absolute, fixed)
7. **Flexbox gap** es mejor que usar margin para espaciado entre elementos
8. **rem** es mejor que **px** para responsive design
9. **Mobile-first** significa empezar con estilos móviles y añadir media queries para pantallas grandes
10. **Box-sizing: border-box** facilita mucho el cálculo de tamaños

---

## 🎓 PATRONES COMUNES DEL PROYECTO

### Layout típico de página
```css
body {
    min-height: 100vh;
    display: flex;
    flex-direction: column;
}

main {
    flex: 1;  /* Empuja footer al fondo */
}
```

### Botones con efecto hover
```css
.boton {
    border-radius: 30px;
    transition: all 0.3s;
    cursor: pointer;
}

.boton:hover {
    background: #000;
    transform: scale(1.05);
}
```

### Sección con layout 2 columnas
```css
.seccion {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 2rem;
    align-items: center;
}

@media (max-width: 768px) {
    .seccion {
        grid-template-columns: 1fr;
    }
}
```

---

¡Buena suerte en tu examen! 🚀💪