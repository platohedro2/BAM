# Paginas en Astro

Las **páginas** son [componentes de Astro](https://docs.astro.build/es/core-concepts/astro-components/) que se encuentran en la subcarpeta `src/pages/`. Ellas son las responsables de manejar el enrutamiento, la carga de datos y el diseño general de cada página HTML de tu proyecto.

### Tipos de página compatibles <a href="#tipos-de-pagina-compatibles" id="tipos-de-pagina-compatibles"></a>

[Section titled Tipos de página compatibles](https://docs.astro.build/es/core-concepts/astro-pages/#tipos-de-p%C3%A1gina-compatibles)

Astro es compatible con los siguientes tipos de archivos en el directorio `src/pages/`:

* [`.astro`](https://docs.astro.build/es/core-concepts/astro-pages/#p%C3%A1ginas-de-astro)
* [`.md`](https://docs.astro.build/es/core-concepts/astro-pages/#p%C3%A1ginas-markdownmdx)
* `.mdx` (con la [integración de MDX (EN)](https://docs.astro.build/es/guides/integrations-guide/mdx/#installation)) instalada
* [`.html`](https://docs.astro.build/es/core-concepts/astro-pages/#p%C3%A1ginas-html)
* \[`.js`/`.ts`] (como [endpoints](https://docs.astro.build/es/core-concepts/endpoints/))

### Enrutamiento basado en archivos <a href="#enrutamiento-basado-en-archivos" id="enrutamiento-basado-en-archivos"></a>

[Section titled Enrutamiento basado en archivos](https://docs.astro.build/es/core-concepts/astro-pages/#enrutamiento-basado-en-archivos)

Astro aprovecha una estrategia de enrutamiento llamada **enrutamiento basado en archivos**. Cada archivo `.astro` en la carpeta `src/pages` se convierte en una página o un endpoint en tu proyecto de acuerdo a su ruta.

Un archivo puede generar múltiples páginas usando [enrutamiento dinámico](https://docs.astro.build/es/core-concepts/routing/#rutas-din%C3%A1micas). Esto te permite crear páginas incluso si tu contenido está fuera del directorio especial `/pages/`, como en una [colección de contenido (EN)](https://docs.astro.build/es/guides/content-collections/) o un [CMS](https://docs.astro.build/es/guides/cms/).

📚 Lea más sobre [enrutamiento en Astro](https://docs.astro.build/es/core-concepts/routing/)

#### Link entre páginas <a href="#link-entre-paginas" id="link-entre-paginas"></a>

[Section titled Link entre páginas](https://docs.astro.build/es/core-concepts/astro-pages/#link-entre-p%C3%A1ginas)

Escriba HTML estándar [elementos `<a>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/a) en tus páginas Astro para enlazar a otras páginas en tu sitio.

### Páginas de Astro <a href="#paginas-de-astro" id="paginas-de-astro"></a>

[Section titled Páginas de Astro](https://docs.astro.build/es/core-concepts/astro-pages/#p%C3%A1ginas-de-astro)

Las páginas de Astro utilizan la extensión `.astro` y tienen las mismas funcionalidades que los [componentes de Astro](https://docs.astro.build/es/core-concepts/astro-components/).

```
---
---
<html lang="es">
  <head>
    <title>Mi página de inicio</title>
  </head>
  <body>
    <h1>Bienvenido a mi sitio web</h1>
  </body>
</html>
```

Para evitar repetir los mismos elementos HTML en cada página, puedes mover los elementos comunes `<head>` y `<body>` a sus propios [componentes de plantilla](https://docs.astro.build/es/core-concepts/layouts/). Puedes usar tantos o tan pocos componentes de plantilla como desees.

```
---
import MySiteLayout from '../layouts/MySiteLayout.astro';
---
<MySiteLayout>
  <p>El contenido de mi página envuelto en un componente de plantilla</p>
</MySiteLayout>
```

📚 Lea más sobre [componentes de plantilla](https://docs.astro.build/es/core-concepts/layouts/) en Astro.

### Páginas Markdown/MDX <a href="#paginas-markdownmdx" id="paginas-markdownmdx"></a>

[Section titled Páginas Markdown/MDX](https://docs.astro.build/es/core-concepts/astro-pages/#p%C3%A1ginas-markdownmdx)

Astro trata archivos Markdown (`.md`) dentro de `src/pages/` como páginas en tu proyecto. Si tienes la [integración de MDX instalada (EN)](https://docs.astro.build/es/guides/integrations-guide/mdx/#installation), también procesa los archivos MDX (`.mdx`) de la misma manera. Estos se usan comúnmente para páginas con mucho texto, como artículos de blog y documentación.

[Las colecciones de contenido de páginas Markdown o MDX (EN)](https://docs.astro.build/es/guides/content-collections/) en `src/content/` pueden ser usadas para [generar páginas dinámicamente](https://docs.astro.build/es/core-concepts/routing/#rutas-din%C3%A1micas).

Las plantillas de página son especialmente útiles para [archivos Markdown](https://docs.astro.build/es/core-concepts/astro-pages/#p%C3%A1ginas-markdownmdx). Los archivos Markdown pueden usar la propiedad de frontmatter `layout` para especificar un [componente de plantilla](https://docs.astro.build/es/core-concepts/layouts/) que envolverá el contenido de Markdown en un documento de página `<html>...</html>`.

```
---
layout: '../layouts/MySiteLayout.astro'
title: 'Mis páginas Markdown'
---
# Título

Esta es mi página, escrita en **Markdown.**
```

📚 Lea más sobre [Markdown](https://docs.astro.build/es/guides/markdown-content/) en Astro.

### Páginas HTML <a href="#paginas-html" id="paginas-html"></a>

[Section titled Páginas HTML](https://docs.astro.build/es/core-concepts/astro-pages/#p%C3%A1ginas-html)

Los archivos `.html` pueden ser colocados en `src/pages/` y usados directamente como páginas en tu proyecto. Ten en cuenta que algunas funcionalidades clave de Astro no son compatibles con [Componentes HTML](https://docs.astro.build/es/core-concepts/astro-components/#componentes-html).

### Página de error 404 personalizada <a href="#pagina-de-error-404-personalizada" id="pagina-de-error-404-personalizada"></a>

[Section titled Página de error 404 personalizada](https://docs.astro.build/es/core-concepts/astro-pages/#p%C3%A1gina-de-error-404-personalizada)

Para crear una página de error 404 personalizada, puedes crear un archivo `404.astro` o `404.md` en `/src/pages`.

Esto generará una página `404.html` que la mayoría de los [servicios de despliegue](https://docs.astro.build/es/guides/deploy/) encontrarán y usarán.
