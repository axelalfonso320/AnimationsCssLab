# 🎬 Laboratorio: Animaciones CSS con Templates

Este laboratorio tiene como objetivo explorar, adaptar e implementar animaciones CSS creadas con plantillas de terceros en un sitio web real. Aprenderás a usar selectores CSS para aplicar animaciones, trabajar con `@keyframes` y entregar tu trabajo mediante un Pull Request en GitHub.

---

## 1) Requisitos previos

- Un navegador moderno (Chrome, Edge, Firefox, Safari).
- Un editor de código (se recomienda VS Code).
- Git instalado en tu computadora.
- Conocimientos básicos de HTML y CSS.

---

## 2) Archivos del proyecto

| Archivo / Carpeta | Función |
|---|---|
| `index.html` | La página web con las tarjetas (cards) |
| `css/animations.css` | Archivo CSS donde aplicarás las animaciones |
| `img/` | Imágenes usadas en las tarjetas |
| `js/` | Scripts de soporte |
| `readme.md` | Este tutorial |

> 📝 Durante el laboratorio crearás un archivo llamado `entregable.txt` donde escribirás tus respuestas a las preguntas de cada paso.

---

## 3) Objetivos de aprendizaje

Al terminar este laboratorio podrás:

- Identificar y describir el comportamiento de animaciones CSS ya implementadas.
- Aplicar animaciones CSS usando distintos selectores (`:hover`, `:active`, clases, etc.).
- Usar `@keyframes` para definir animaciones personalizadas.
- Copiar e integrar animaciones de la herramienta [Animista](https://animista.net/).
- Subir tu trabajo en una rama separada y solicitar un Pull Request en GitHub.

---

## 4) Pasos del laboratorio

---

### Paso 1 — Explora las animaciones existentes

1. Clona el repositorio en tu computadora:

```bash
git clone "{url del repositorio}"
```

2. Abre `index.html` en tu navegador.
3. Observa las tarjetas (cards) en pantalla.
4. Haz clic sobre una tarjeta y mantén el botón presionado.
5. En tu archivo `entregable.txt`, responde:

> **Pregunta 1:** ¿Qué está sucediendo visualmente cuando mantienes el clic sobre una card? ¿Qué propiedad o selector CSS crees que lo provoca?

---

### Paso 2 — Modifica selectores CSS y observa los cambios

#### 2.1 — Animación al cargar la página

Abre `css/animations.css` y localiza el bloque `.card{}`. Modifícalo de la siguiente manera:

```css
.card {
    -webkit-animation: slit-in-diagonal-2 450ms linear both;
    animation: slit-in-diagonal-2 450ms linear both;
}
```

Recarga la página en el navegador y responde en `entregable.txt`:

> **Pregunta 2:** ¿Qué cambió en el comportamiento de las cards al recargar la página?

#### 2.2 — Animación al pasar el cursor

Ahora cambia el selector para que la animación se active únicamente al pasar el mouse encima:

```css
.card:hover {
    -webkit-animation: slit-in-diagonal-2 450ms linear both;
    animation: slit-in-diagonal-2 450ms linear both;
}
```

Recarga el sitio y pasa el cursor sobre las tarjetas.

#### 2.3 — Experimenta con otros selectores

Consulta la referencia de selectores CSS en [W3Schools — CSS Selectors](https://www.w3schools.com/cssref/css_selectors.php) y elige **3 selectores distintos**. Aplícalos al elemento `.card` y prueba su comportamiento.

En `entregable.txt`, responde:

> **Pregunta 3:** ¿Qué 3 selectores elegiste? Describe brevemente qué hace cada uno y cómo se comportó la animación al usarlo.

---

### Paso 3 — Integra una animación desde Animista

[Animista](https://animista.net/) es una herramienta en línea que genera animaciones CSS listas para usar.

1. Entra a [https://animista.net/](https://animista.net/).
2. Navega a la categoría de animaciones de **background** y selecciona una que te llame la atención.
3. Copia el código `@keyframes` generado y pégalo al final de `css/animations.css`. Por ejemplo:

```css
/* ANIMACIÓN DE FONDO — kenburns-top */
@-webkit-keyframes kenburns-top {
    0% {
        -webkit-transform: scale(1) translateY(0);
                transform: scale(1) translateY(0);
        -webkit-transform-origin: 50% 16%;
                transform-origin: 50% 16%;
    }
    100% {
        -webkit-transform: scale(1.25) translateY(-15px);
                transform: scale(1.25) translateY(-15px);
        -webkit-transform-origin: top;
                transform-origin: top;
    }
}
@keyframes kenburns-top {
    0% {
        -webkit-transform: scale(1) translateY(0);
                transform: scale(1) translateY(0);
        -webkit-transform-origin: 50% 16%;
                transform-origin: 50% 16%;
    }
    100% {
        -webkit-transform: scale(1.25) translateY(-15px);
                transform: scale(1.25) translateY(-15px);
        -webkit-transform-origin: top;
                transform-origin: top;
    }
}
```

4. Aplica la animación a las imágenes de las tarjetas usando un selector adecuado:

```css
.card-img-top:hover {
    -webkit-animation: kenburns-top 5s ease-out both;
    animation: kenburns-top 5s ease-out both;
}
```

5. En `entregable.txt`, responde:

> **Pregunta 4:** ¿Para qué sirve un `@keyframes` en CSS? Explícalo con tus propias palabras.

> **Pregunta 5:** Elige 3 propiedades de las animaciones que usaste (por ejemplo: `animation-duration`, `animation-timing-function`, `transform`) y explica qué hace cada una. Ejemplo de formato:
>
> ```
> transform — Permite modificar elementos: pueden ser trasladados, rotados,
> escalados o sesgados de acuerdo con los valores establecidos.
> ```

---

### Paso 4 — Implementa animaciones adicionales

1. Agrega una animación de texto a algún elemento del **navbar** (por ejemplo, al título o a los enlaces).
2. Agrega una animación a los **botones de las tarjetas** que se active:
   - Al pasar el cursor encima (`:hover`)
   - Al hacer clic (`:active`)

> 💡 **Tip:** Puedes buscar animaciones de tipo "scale", "shake" o "bounce" en Animista para los botones.

---

### Paso 5 — Entrega tu trabajo

1. Guarda todos tus cambios.
2. Crea el archivo `entregable.txt` si aún no lo tienes, y asegúrate de que contenga todas tus respuestas.
3. Agrega los archivos modificados:

```bash
git add entregable.txt
git add css/animations.css
```

4. Crea una nueva rama llamada `entregable`:

```bash
git branch entregable
git checkout entregable
```

5. Realiza el commit y sube la rama:

```bash
git commit -m "entregable animaciones CSS"
git push origin entregable
```

6. Ve a GitHub y abre un **Pull Request** desde la rama `entregable` hacia `main`.

---

## 5) Referencia rápida

| Concepto | Descripción |
|---|---|
| `animation` | Propiedad abreviada para definir una animación CSS |
| `animation-duration` | Tiempo que tarda la animación en completarse |
| `animation-timing-function` | Curva de velocidad (`linear`, `ease`, `ease-in-out`, etc.) |
| `animation-delay` | Tiempo de espera antes de que inicie la animación |
| `animation-iteration-count` | Número de veces que se repite (`infinite` para bucle) |
| `animation-fill-mode` | Estado del elemento antes/después de la animación (`both`, `forwards`) |
| `@keyframes` | Define los estados intermedios de una animación |
| `transform` | Aplica traslaciones, rotaciones, escala o sesgo a un elemento |
| `:hover` | Selector que se activa al pasar el cursor sobre el elemento |
| `:active` | Selector que se activa mientras se mantiene pulsado el elemento |

---

## 6) Recursos útiles

- [Animista — Generador de animaciones CSS](https://animista.net/)
- [MDN — CSS Animations](https://developer.mozilla.org/es/docs/Web/CSS/CSS_animations/Using_CSS_animations)
- [W3Schools — CSS Selectors](https://www.w3schools.com/cssref/css_selectors.php)
- [MDN — @keyframes](https://developer.mozilla.org/es/docs/Web/CSS/@keyframes)

---

*Laboratorio Animaciones CSS — FCA Informática UNAM*
