---
theme: apple-basic
title: "CSS: El arte de organizar con estilo"
titleTemplate: "%s - odraciRdev"
info: |
  Aprende a construir layouts web modernos y responsivos usando Flexbox y CSS Grid. En este taller 100% práctico, exploraremos las herramientas más potentes de CSS para maquetar páginas web, con ejemplos en vivo, ejercicios interactivos y tips. Ideal para personas que están dando sus primeros pasos en el desarrollo front-end o que quieren mejorar sus habilidades de maquetación.
author: Ricardo Cuauro
keywords: css,flex,grid,workshop
colorSchema: dark
favicon: "https://odracir.dev/favicons/favicon-48x48.png"
transition: slide-left
mdc: true
seoMeta:
  ogTitle: "CSS: El arte de organizar con estilo"
  ogDescription: Aprende a construir layouts web modernos y responsivos usando Flexbox y CSS Grid. En este taller 100% práctico, exploraremos las herramientas más potentes de CSS para maquetar páginas web, con ejemplos en vivo, ejercicios interactivos y tips. Ideal para personas que están dando sus primeros pasos en el desarrollo front-end o que quieren mejorar sus habilidades de maquetación.
  ogImage: https://odracir.dev/og/og.jpg
layout: intro-image
---

<main>
  <h1 class="title">CSS: El arte de organizar con estilo</h1>

  <a href="https://uxcorprangel.github.io/" target="_blank" class="uxcorp-link">
    <img 
      src="/assets/uxcorp-logo.webp" 
      alt="UXCorp Logo" 
      class="uxcorp"
    />
  </a>

  <div class="buttons">
    <a href="https://linkedin.com/in/ricardocuauro" target="_blank" class="slidev-icon-btn">
      <carbon:logo-linkedin />
    </a>
    <a href="https://github.com/odracirdev" target="_blank" class="slidev-icon-btn">
      <carbon:logo-github />
    </a>
  </div>
</main>

<style>
  main {
    height: 100%;
    width: 100%;
    background-image: url("/assets/slides-bg-1.webp");
    background-repeat: no-repeat;
    background-size: cover;
    padding-left: 3.5rem;
    padding-right: 3.5rem;
    padding-top: 2.5rem;
    padding-bottom: 2.5rem;

    .title {
      text-align: center;
      text-wrap: balance;
      font-size: 3.75rem;
    }

     .uxcorp-link {
      display: block;
      width: fit-content;
      margin: 62px auto 0;
      border: none;

      .uxcorp {
        max-width: 220px;
      }
    }

    .buttons {
      position: absolute;
      right: 20px;
      bottom: 20px;
    }
  }

  .slidev-layout {
    padding: 0 !important;
  }
</style>

---
transition: fade-out
title: Introducción
layout: two-cols
---

<h1>¡Hola! Me llamo Ricardo.</h1>

<ul>
  <li v-click>Soy desarrollador web autodidacta.</li>
  <li v-click>También streamer de código (En pausa).</li>
  <li v-click>Trabajo en Cencosud.</li>
  <li v-click>Me gusta el open source y las comunidades como esta.</li>
</ul>

<h2 v-click>¿Qué vamos a ver hoy?</h2>

<ul>
  <li v-click>Introducción a CSS moderno</li>
  <li v-click>Flexbox desde cero</li>
  <li v-click>CSS Grid desde cero</li>
  <li v-click>Flex vs Grid</li>
</ul>

<p v-click>Si nos da tiempo... <strong>¡Un proyecto final!</strong> <span v-mark.circle.blue="10">Con premio</span></p>

::right::

<img src="/assets/odracir.webp" alt="odraciR" class="avatar">

<style>
  .avatar {
    max-width: 200px;
    margin: 0 auto;
  }
</style>

---
transition: slide-up
title: ¿Qué es CSS?
layout: statement
---
Pero antes de comenzar...

# ¿Qué es CSS?

---
transition: slide-up
title: Definición de CSS (Manz)
layout: quote
---
# "CSS es un lenguaje de estilos para dotar de apariencia y aspecto visual a una página o sitio web (entre otras cosas). También es conocido como el mayor enemigo de los programadores backend."
ManzDev

---
transition: slide-up
title: CSS Moderno
layout: statement
---

Momento "teórico" 🫣
# Introducción a CSS moderno

<img src="/assets/css3-css6.avif" alt="CSS 3 a CSS 6" style="max-width: 300px; display: block; margin: auto;">

---
title: "CSS Moderno: antes vs ahora 1"
---

# CSS Moderno: antes vs ahora


<h2 style="margin-top: 16px;">Agrupación de selectores</h2>

Reescribir de forma más compacta y sencilla los selectores múltiples combinados. <a href="https://lenguajecss.com/css/selectores/combinadores-logicos/#el-combinador-is" target="_blank">Más info</a>

````md magic-move {lines: true}
```css
/* Antes */
.container .item,
.container .parent,
.container .element {
  /* ... */
}
```

```css
/* Ahora */
.container :is(.item, .parent, .element) {
  /* ... */
}
```
````

<v-click>
<h2 style="margin-top: 16px;">Escribir colores</h2>

Escribir colores RGB con canales alfa (transparencias). <a href="https://lenguajecss.com/css/colores/funcion-rgb/#la-funci%C3%B3n-rgb" target="_blank">Más info</a>

````md magic-move {lines: true}
```css
/* Antes */
.container {
  background: rgba(255, 255, 0, 0.5);
}
```

```css
/* Ahora */
.container {
  background: rgb(100% 100% 0 / 50%);
}
```
````
</v-click>

---
title: "CSS Moderno: antes vs ahora 2"
---

# CSS Moderno: antes vs ahora

<h2 style="margin-top: 16px;">Anidar código CSS</h2>

Crear componentes CSS nativos autocontenidos dentro de otros. <a href="https://lenguajecss.com/css/calidad-de-codigo/css-nesting/" target="_blank">Más info</a>


````md magic-move {lines: true}
```css
/* Antes */
.parent {
  background: grey;
}

.parent .element {
  background: darkred;
}

.parent .element:hover {
  background: red;
}
```

```css
/* Ahora */
.parent {
  background: grey;

  & .element {
    background: darkred;

    &:hover {
      background: red;
    }
  }
}
```
````

---
title: "CSS Moderno: antes vs ahora 3"
---

# CSS Moderno: antes vs ahora

<h2 style="margin-top: 16px;">Centrar el contenido de un elemento</h2>

Realizar un centrado en ambos ejes directamente, con una sola propiedad. <a href="https://lenguajecss.com/css/maquetacion-y-colocacion/grid-css-alinear/" target="_blank">Más info</a>


````md magic-move {lines: true}
```css
/* Antes */
.parent {
  display: grid;
  justify-items: center;
  align-items: center;
}
```

```css
/* Ahora */
.parent {
  display: grid;
  place-items: center;
}
```
````

<v-click>
<h2 style="margin-top: 16px;">Reutilizar información</h2>

Utilizar custom properties para guardar información en variables. <a href="https://lenguajecss.com/css/cascada-css/css-custom-properties/" target="_blank">Más info</a>


````md magic-move {lines: true}
```css
/* Antes */
.parent {
  width: 300px;
  height: 300px;
  background: grey;
}
```

```css
/* Ahora */
.parent {
  --size: 300px;

  width: var(--size);
  height: var(--size);
  background: var(--color, grey);
}
```
````
</v-click>

---
title: "CSS Moderno: antes vs ahora 4"
---

# CSS Moderno: antes vs ahora

<h2 style="margin-top: 16px;">Sintaxis flexible de rangos</h2>

Posibilidad de utilizar una sintaxis más amigable para media queries. <a href="https://lenguajecss.com/css/responsive-web-design/media-queries/#media-query-range-syntax" target="_blank">Más info</a>


````md magic-move {lines: true}
```css
/* Antes */
@media (min-width: 800px) and
       (max-width: 1280px) {
  .menu {
    background: red;
  }
}
```

```css
/* Ahora */
@media (800px <= width <= 1280px) {
  .menu {
    background: red;
  }
}
```
````

---
transition: slide-up
title: ¿Por qué usamos Flexbox y Grid hoy en día?
layout: statement
---

Un poquito más de cháchara... 🙊
# ¿Por qué usamos Flexbox y Grid hoy en día?

---
transition: slide-up
title: Demo 1
layout: statement
---

# Demostración

<a href="https://codepen.io/Ricardo-Cuauro/full/GgJpzMY" target="_blank">Flexbox y Grid</a>

<a href="https://codepen.io/Ricardo-Cuauro/full/EajVrLm" target="_blank">Comparación de Layouts</a>

Extra

<div style="display: flex; justify-content: center; gap: 24px; margin-bottom: 16px;">
  <a href="https://web.archive.org/web/20061201035518/http://www.habbo.es/" target="_blank">Habbo (2006)</a>
  <a href="view-source:https://web.archive.org/web/20061201035518/http://www.habbo.es/" target="_blank">Código fuente</a>
</div>
<div style="display: flex; justify-content: center; gap: 24px;">
  <a href="https://www.habbo.es/" target="_blank">Habbo (actualidad)</a>
  <a href="view-source:https://www.habbo.es/" target="_blank">Código fuente</a>
</div>

---
transition: slide-up
title: Flexbox desde cero
layout: statement
---

¡Ahora sí! A lo que vinimos 🍻
# Flexbox desde cero

---
transition: slide-up
title: "Flexbox: Conceptos clave"
layout: two-cols
layoutClass: gap-8
---

<small>Te la creíste... Seguimos con teoría 🤭</small>
# Flexbox desde cero
## Conceptos clave

<small v-click>Pero te prometo que serán cortos y fáciles de entender 🥹</small>

<ul>
  <li v-click><code>display: flex</code></li>
  <li v-click><code>flex-direction</code>, <code>justify-content</code>, <code>align-items</code></li>
  <li v-click><code>flex-wrap</code>, <code>gap</code></li>
  <li v-click><code>flex-grow</code>, <code>flex-shrink</code>, <code>flex-basis</code></li>
</ul>

<v-click>
<h1>¿Entendieron?</h1>
<small>El que diga que no es backend de los buenos 🤣</small>
</v-click>

::right::

<div style="height: 100%; display: flex; align-items: center;">
  <img v-if="$slidev.nav.clicks === 2" src="/assets/flex/display-flex.webp" alt="display: flex">
  <img v-if="$slidev.nav.clicks === 3" src="/assets/flex/flex-direction.webp" alt="flex-direction">
  <img v-if="$slidev.nav.clicks === 4" src="/assets/flex/justify-content.webp" alt="justify-content">
  <img v-if="$slidev.nav.clicks >= 5" src="/assets/flex/flex-combinations.webp" alt="flex combinations">
</div>


---
transition: slide-up
title: Ejercicios flex
layout: statement
---

Ahora es tu turno 🫵🏻
# 🧑🏻‍💻 Ejercicios prácticos

---
transition: slide-up
title: Ejercicios flex 1
layout: fact
---

# Ejercicio 1
<v-click>Centrar un botón en el medio de la pantalla (horizontal y vertical).</v-click>
<a v-click href="https://codepen.io/Ricardo-Cuauro/pen/QwbjPyQ" target="_blank">Comenzar</a>

---
transition: slide-up
title: Ejercicios flex 2
layout: fact
---

# Ejercicio 2
<v-click>Tarjetas de productos con misma altura y alineación flexible.</v-click>
<a v-click href="https://codepen.io/Ricardo-Cuauro/pen/VYLvNKe" target="_blank">Comenzar</a>

---
transition: slide-up
title: Ejercicios flex 3
layout: fact
---

# ¡Desafío grupal!
<v-click>Diseñar un layout de perfil de usuario usando sólo Flexbox.</v-click>
<a v-click href="https://codepen.io/Ricardo-Cuauro/pen/myJegmR" target="_blank">Comenzar</a>

---
transition: slide-up
title: Grid desde cero
layout: statement
---

🚨 Nooooo ¡La polizia! Nooo 🚨
# Grid desde cero

---
transition: slide-up
title: "Grid: Conceptos clave"
layout: two-cols
layoutClass: gap-8
---

<small>No teman, ya verán lo fácil que es 😉</small>
# Grid desde cero
## Conceptos clave

<ul>
  <li v-click><code>display: grid</code></li>
  <li v-click><code>grid-template-columns</code>, <code>grid-template-rows</code></li>
  <li v-click><code>grid-row</code>, <code>grid-column</code>, <code>gap</code></li>
  <li v-click><code>grid-template-areas</code></li>
</ul>

<h2 v-click>¿Viste que es fácil? 🐣</h2>

::right::

<div style="height: 100%; display: flex; align-items: center;">
  <img v-if="$slidev.nav.clicks <= 5" src="/assets/grid/display-grid.webp" alt="display: grid">
</div>


---
transition: slide-up
title: Ejercicios grid
layout: statement
---

Ahora es tu turno 🫵🏻 (Si, otra vez)
# 🧑🏻‍💻 Ejercicios prácticos

---
transition: slide-up
title: Ejercicios grid 1
layout: fact
---

# Ejercicio 3
<v-click>Crear un layout de blog (header, sidebar, main, footer).</v-click>
<p v-click><small>Puede ser grupal 😉</small></p>
<a v-click href="https://codepen.io/Ricardo-Cuauro/pen/JodYqjb" target="_blank">Comenzar</a>

---
transition: slide-up
title: Ejercicios grid 2
layout: fact
---

# Ejercicio 4
<v-click>Galería de imágenes responsive (Sin media query).</v-click>
<p v-click><small>Puede ser grupal 😉</small></p>
<a v-click href="https://codepen.io/Ricardo-Cuauro/pen/vEONwEW" target="_blank">Comenzar</a>


---
transition: slide-up
title: Flex vs grid
layout: statement
---

¡Lo logramos! Llegamos vivos al final 🤪
# Flex vs Grid

---
transition: slide-up
title: Proyecto final
layout: statement
---

Lo prometido es deuda...
# ¡Proyecto final!

<v-click>Para quienes quieran llevarse una recompensa 🪅</v-click>

---
transition: slide-up
title: Definición del proyecto
layout: two-cols
---

# Build Challenge

Crea una página responsive de portafolio personal (sencilla) que combine Flex y Grid.

<v-click>Debe tener:</v-click>

<ul>
  <li v-click>Header con navegación</li>
  <li v-click>Sección "Sobre mí"</li>
  <li v-click>Galería o sección de proyectos</li>
  <li v-click>Footer</li>
</ul>

<h2 v-click>¡Vamos que está fácil!</h2>

<v-click>No es obligatorio.</v-click>

::right::

<h1 v-click>¿Cuál es el premio?</h1>

<v-click>Una polera de tu lenguaje de programación favorito o incluso una tecnología. Por ejemplo...</v-click>

<div style="display: flex; justify-content: center; margin: 20px; 0">
  <img v-click src="/assets/CSS-is-Awesome-Black-Front.webp" alt="CSS Is Awesome" style="max-width: 300px;">
</div>

<v-click>Para ganar solo debes terminar primero. 😉</v-click>

---
transition: slide-up
title: Gracias
layout: image
---

<main class="container">
  <h1>¡Gracias!</h1>

  <a href="https://www.duoc.cl/" target="_blank" style="border: none;">
      <img 
        src="/assets/duoc-uc.webp" 
        alt="Duoc UC Logo"
        style="max-width: 260px"
      />
    </a>

  <div class="communities">
    <a href="https://uxcorprangel.github.io/" target="_blank">
      <img 
        src="/assets/uxcorp-logo.webp" 
        alt="UXCorp Logo"
      />
    </a>
    <a href="https://techschool.lat/" target="_blank">
      <img 
        src="/assets/techschool-logo.webp"
        alt="Techscool Logo"
      />
    </a>
    <a href="https://storefordevs.com/" target="_blank">
      <img 
        src="/assets/store-for-devs.webp"
        alt="Store for devs Logo"
      />
    </a>
  </div>
</main>

<style>
  .container {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 64px;
    background-image: url("/assets/slides-bg-1.webp");
    background-repeat: no-repeat;
    background-size: cover;

    h1 {
      font-size: 3.75rem;
    }

    .communities {
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 48px;

      a {
        border: none;
      }

      & img {
        max-height: 160px;
      }    
    }
  }

  .slidev-layout {
    padding: 0 !important;
  }
</style>
