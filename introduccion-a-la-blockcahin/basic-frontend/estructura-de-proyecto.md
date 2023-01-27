# Estructura de proyecto

## Estructura de proyecto <a href="#overview" id="overview"></a>

Tu nuevo proyecto Astro generado a partir del asistente de instalación `create astro` incluye algunos archivos y carpetas por defecto. Otros, los crearás tú mismo y los agregarás a la estructura de archivos existente.

Así es como se organiza un proyecto de Astro y algunos archivos que encontrarás en tu nuevo proyecto.

### Carpetas y archivos <a href="#carpetas-y-archivos" id="carpetas-y-archivos"></a>

[Section titled Carpetas y archivos](https://docs.astro.build/es/core-concepts/project-structure/#carpetas-y-archivos)

Astro propone una estructura de carpetas opinionada para tu proyecto. La raíz de tu proyecto deberá incluir los siguientes archivos y carpetas:

* `src/*` - El código fuente de tu proyecto (componentes, páginas, estilos, etc.)
* `public/*` - Archivos sin código que no serán procesados (fuentes, íconos, etc.)
* `package.json` - El manifiesto de tu proyecto
* `astro.config.mjs` - El archivo de configuración de Astro (recomendado)
* `tsconfig.json` - El archivo de configuración de Typescript (recomendado)

#### Ejemplo de árbol de proyecto <a href="#ejemplo-de-arbol-de-proyecto" id="ejemplo-de-arbol-de-proyecto"></a>

[Section titled Ejemplo de árbol de proyecto](https://docs.astro.build/es/core-concepts/project-structure/#ejemplo-de-%C3%A1rbol-de-proyecto)

Un proyecto de Astro común debería verse así:

*

public/

*
* robots.txt
*
* favicon.svg
*
*
  * social-image.png
*

src/

*

components/

*
* Header.astro
*
*
  * Button.jsx
*

layouts/

*
*
  * PostLayout.astro
*

pages/

*

posts/

*
* post1.md
*
* post2.md
*
*
  * post3.md
*
*
  * index.astro
*

styles/

*
*
  *
    * global.css
*
* astro.config.mjs
*
* package.json
*
* tsconfig.json

#### `src/` <a href="#src" id="src"></a>

[Section titled src/](https://docs.astro.build/es/core-concepts/project-structure/#src)

La carpeta `src/` es donde se encuentra el código fuente de tu proyecto. Esto incluye:

* [Páginas](https://docs.astro.build/es/core-concepts/astro-pages/)
* [Layout](https://docs.astro.build/es/core-concepts/layouts/)
* [Componentes de Astro](https://docs.astro.build/es/core-concepts/astro-components/)
* [Componentes de framework (React, etc.)](https://docs.astro.build/es/core-concepts/framework-components/)
* [Estilos (CSS, Sass)](https://docs.astro.build/es/guides/styling/)
* [Markdown](https://docs.astro.build/es/guides/markdown-content/)

Astro procesa, optimiza y empaqueta los archivos en `src/` para crear la website final que será desplegada al navegador. A diferencia de la carpeta estática `public/`, los archivos en `src/` serán procesados por Astro.

Algunos archivos (como los componentes de Astro) no serán enviados al navegador como fueron escritos, sino que serán renderizados a HTML estático. Otros archivos (como CSS) serán enviados directamente al navegador, pero antes serán optimizados o empaquetados con otros archivos para un mejor rendimiento.

#### `src/components` <a href="#srccomponents" id="srccomponents"></a>

[Section titled src/components](https://docs.astro.build/es/core-concepts/project-structure/#srccomponents)

Los **componentes** son unidades reutilizables de código para tus páginas HTML. Estos componentes pueden ser [componentes de Astro](https://docs.astro.build/es/core-concepts/astro-components/) o [componentes de framework](https://docs.astro.build/es/core-concepts/framework-components/) como React o Vue. Es común agrupar y organizar todos tus componentes en una sola carpeta.

Esta es la convención común en proyectos de Astro, pero no es necesaria. ¡Siéntete libre de organizar tus componentes a gusto!

#### `src/layouts` <a href="#srclayouts" id="srclayouts"></a>

[Section titled src/layouts](https://docs.astro.build/es/core-concepts/project-structure/#srclayouts)

[Plantillas](https://docs.astro.build/es/core-concepts/layouts/) son componentes especiales que envuelven el contenido en una página. Estas son comúnmente utilizadas por [páginas de Astro](https://docs.astro.build/es/core-concepts/astro-pages/) y [páginas Markdown o MDX](https://docs.astro.build/es/guides/markdown-content/) para definir una plantilla común entre todas tus páginas.

Así como `src/components`, esta carpeta es una convención común pero no es necesaria.

#### `src/pages` <a href="#srcpages" id="srcpages"></a>

[Section titled src/pages](https://docs.astro.build/es/core-concepts/project-structure/#srcpages)

[Páginas](https://docs.astro.build/es/core-concepts/astro-pages/) son componentes especiales usados para crear páginas en tu proyecto. Una página puede ser un componente de Astro o un archivo Markdown.

&#x20;Precaución

¡`src/pages` es una carpeta **necesaria** en tu proyecto de Astro! ¡Sin ella, tu proyecto no tendrá páginas o rutas!

#### `src/styles` <a href="#srcstyles" id="srcstyles"></a>

[Section titled src/styles](https://docs.astro.build/es/core-concepts/project-structure/#srcstyles)

Es una convención común para guardar todos tus archivos CSS o Sass en una sola carpeta `src/styles` pero no es necesaria. Siempre y cuando tus estilos se encuentren dentro de la carpeta `src/` y sean importados correctamente, Astro se encargará de optimizarlos.

#### `public/` <a href="#public" id="public"></a>

[Section titled public/](https://docs.astro.build/es/core-concepts/project-structure/#public)

La carpeta `public/` es para archivos que no necesiten ser procesados durante la compilación final de tu proyecto. Estos archivos serán copiados dentro de la carpeta build sin ser modificados.

Este comportamiento hace que `public/` sea ideal para activos comunes como imágenes y fuentes, o archivos especiales como `robots.txt` y `manifest.webmanifest`.

Puedes colocar CSS y JavaScript en tu carpeta `public/`, pero ten en cuenta que esos archivos no se empaquetarán ni optimizarán en la compilación final.

&#x20;Sugerencia

Como regla general, cualquier archivo CSS o JavaScript que escribas debe estar en tu carpeta `src/`.

#### `package.json` <a href="#packagejson" id="packagejson"></a>

[Section titled package.json](https://docs.astro.build/es/core-concepts/project-structure/#packagejson)

Es un archivo utilizado por los gestores de paquetes de JavaScript para administrar tus dependencias. También define los scripts que se usan comúnmente para ejecutar Astro (ex: `npm start`, `npm run build`).

Hay [dos tipos de dependencias](https://docs.npmjs.com/specifying-dependencies-and-devdependencies-in-a-package-json-file) que puedes especificar en `package.json`: `dependencies` (dependencias) y `devDependencies` (dependencias de desarrollo). En la mayoría de los casos, estas funcionan de la misma manera: Astro necesita todas las dependencias al hacer _build_, y tu gestor de paquetes instalará ambos. Recomendamos poner todas tus dependencias en `dependencies` para comenzar, y solo usar `devDependencies` si encuentras la necesidad de hacerlo.

Para obtener ayuda sobre crear un nuevo archivo `package.json` para tu proyecto, consulta las instrucciones en [instalación manual](https://docs.astro.build/es/install/manual/).

#### `astro.config.mjs` <a href="#astroconfigmjs" id="astroconfigmjs"></a>

[Section titled astro.config.mjs](https://docs.astro.build/es/core-concepts/project-structure/#astroconfigmjs)

Este archivo es generado al crear tu proyecto en Astro e incluye la configuración de tu proyecto. Aquí puedes especificar las integraciones que desees utilizar, las opciones de compilación final, la configuración del servidor, y más.

Lee la [Guía de Configuración de Astro](https://docs.astro.build/es/guides/configuring-astro/) para obtener detalles sobre las opciones de configuración.

#### `tsconfig.json` <a href="#tsconfigjson" id="tsconfigjson"></a>

[Section titled tsconfig.json](https://docs.astro.build/es/core-concepts/project-structure/#tsconfigjson)

Este archivo es generado en cada plantilla de inicio de Astro e incluye la configuración de las opciones de Typescript para tu proyecto de Astro. Algunas características (como importaciones de paquetes de npm) no están soportadas completamente en tu editor sin un archivo `tsconfig.json`.

Lee la [Guía de Typescript](https://docs.astro.build/es/guides/typescript/) para obtener detalles sobre las opciones de configuración.
