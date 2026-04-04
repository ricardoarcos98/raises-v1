# Fundación queFluye — Sitio web (landing)

Sitio estático en un solo archivo HTML que presenta a **Fundación queFluye**, el programa de campañas **Remo**, y enlaza a la **tienda Shopify** para donaciones/compras solidarias.

## Qué incluye el proyecto

| Recurso | Descripción |
|--------|-------------|
| `index.html` | Página completa: estilos CSS embebidos, marcado y JavaScript (navegación, scroll a anclas, carrusel de campañas, galería de imágenes, animaciones reveal). |
| `img/` | Imágenes de campaña (p. ej. `principal.jpeg`, `mug.jpeg`, `stickers.jpg`, `remo.png`). |

No hay build, bundler ni framework: basta con servir los archivos con cualquier servidor estático o abrir `index.html` en local (algunas rutas relativas funcionan mejor con un servidor local).

## Estructura de la página (secciones)

1. **Hero** — Mensaje principal, CTAs: Donar con Remo, Conocer a Remo, Postular tu Remo.
2. **Campañas (`#campanas`)** — Carrusel horizontal con Remo activo (galería, descripción, barra de progreso vía `data-*`, bloque de transparencia, botón a Shopify) y slides “próximamente”.
3. **Cita** — Frase breve de filosofía.
4. **Quiénes somos (`#sobre`)** — Texto institucional y tarjetas (bento) de valores.
5. **Método Remo (`#metodologia`)** — 4 pasos + aviso del kit de difusión post-compra + cierre.
6. **Pie (`#contacto`)** — Enlaces, transparencia, WhatsApp, ubicación.

Secciones comentadas en el HTML: impacto (stats), encuesta Typeform (se pueden reactivar descomentando).

## Enlaces y dominios externos

- **Tienda:** `https://fundacion-que-fluye.myshopify.com/collections/all` (botón “Donar a Remo” en la campaña activa).
- **WhatsApp:** número `+57 312 843 8532` (`wa.me/573128438532`), mensajes prellenados con el nombre de la fundación.

## Vista previa al compartir el enlace (GitHub Pages, WhatsApp, redes)

**GitHub Pages no “elige” una imagen automática** para la miniatura: hace falta **meta etiquetas Open Graph** (`og:image`, etc.) en el `<head>` con **URL absoluta** (https://…/img/remo.png).

En `index.html` ya están configuradas apuntando a `img/remo.png` y a la URL de GitHub Pages del repo [**Remo**](https://github.com/ricardoarcos98/Remo): `https://ricardoarcos98.github.io/Remo/`. Si cambias el **nombre del repo**, el **usuario** o usas **dominio propio**, actualiza en el HTML las URLs de `og:url`, `og:image`, `twitter:image` y `link rel="canonical"`.

Recomendación para `og:image`: **1200×630 px** aprox. (PNG/JPG); si la miniatura no se actualiza en WhatsApp, prueba el depurador de Facebook (Sharing Debugger) para forzar recacheo.

## Edición rápida de la campaña activa

- **Progreso:** en `.campaign-slide__progress` ajustar `data-vendidos`, `data-total` y opcionalmente `data-porcentaje`. Un script pequeño actualiza la barra y los textos.
- **Fechas y textos:** editar el HTML dentro del slide de Remo #1.
- **Imágenes:** rutas bajo `img/`; la galería usa scroll horizontal y flechas + autopase.

## Tipografía y diseño

- **DM Sans:** cuerpo y casi toda la UI.
- **DM Serif Display:** titulares grandes (hero, h2 de secciones, cita destacada).
- Paleta en variables CSS (`:root`): terracota, verdes, crema, carbón.

## JavaScript (incluido al final de `index.html`)

- Nav fija + menú móvil (hamburger).
- Intersection Observer para clases `.reveal`.
- Contadores animados (sección impacto, si está activa).
- Scroll suave a anclas con **offset según altura del navbar** y destinos internos (p. ej. cabeceras de sección).
- Carrusel de campañas (dots) y galería del Remo activo.

## Meta description para Shopify

Shopify usa la descripción en resultados de búsqueda y redes. Conviene **~150–160 caracteres**, un beneficio claro y la marca.

### Opción recomendada (copiar y pegar)

```
Tienda solidaria de Fundación queFluye (Colombia): productos Remo que apoyan escuelas y comunidades. Compra con propósito, transparencia y envío del kit para compartir tu campaña.
```

*(Ajusta si tu política de envío o kit cambia.)*

### Alternativas más cortas

```
Fundación queFluye: compra solidaria Remo — mugs, termos y más para comunidades en Colombia. Cada compra rema por un territorio real.
```

```
Fundación queFluye · Tienda Remo. Productos con impacto en comunidades colombianas. Sin ánimo de lucro, compra transparente.
```

### Alternativa orientada a SEO local

```
Organización sin ánimo de lucro en Colombia. Tienda Remo: productos que financian proyectos en comunidades vulnerables. Fundación queFluye.
```

---

*Última referencia al contenido del sitio: revisar `index.html` para fechas de campaña, NIT y datos legales del pie.*
