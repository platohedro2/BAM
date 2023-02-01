# Componentes en Astro

## Componentes <a href="#overview" id="overview"></a>

**Los componentes de Astro** son los bloques fundamentales para cualquier proyecto de Astro. Están compuestos únicamente por HTML y no poseen ejecución del lado del cliente.

**Si sabes HTML, ya sabes lo suficiente para escribir tu primer componente Astro.**

La sintaxis del componente de Astro es un superconjunto de HTML. Fue [diseñada para sea familiar para alguien con experiencia en HTML o JSX](https://docs.astro.build/es/core-concepts/astro-components/#diferencias-entre-astro-y-jsx), además es compatible con componentes y expresiones de JavaScript. Puedes identificar los componentes Astro por su extensión: `.astro`.

Los componentes de Astro son extremadamente flexibles. Un componente de Astro puede contener **UI reutilizable**, tal como encabezados o una tarjeta de perfil. También puede contener un fragmento pequeño de HTML, o una colección de etiquetas `<meta>` para facilitar nuestro trabajo con el SEO. Los componentes de Astro también pueden contener el layout de una página.

Lo más importante acerca de los componentes de Astro es que **se renderizan a HTML durante la compilación del proyecto**. Aún si posees código JavaScript dentro de tus componentes, este código solo se ejecuta al construir tu proyecto, siendo removido de la página final que se enviará al usuario. El resultado es un sitio web más rápido y sin rastros de JavaScript.

### Estructura de un componente <a href="#estructura-de-un-componente" id="estructura-de-un-componente"></a>

[Section titled Estructura de un componente](https://docs.astro.build/es/core-concepts/astro-components/#estructura-de-un-componente)

Un componente de Astro se compone de dos partes principales: el **script del componente** y el **maquetado del componente**. Cada parte cumple una función diferente, pero juntas proveen un marco de trabajo más fácil de utilizar y lo suficientemente expresivo para manejar cualquier cosa que desees construir.

```
---
// Script del componente (JavaScript)
---
<!-- Maquetado del componente (HTML + Expresiones JS) -->
```

Puedes utilizar componentes dentro de otros componentes para construir una UI más avanzada y compleja. Por ejemplo, el componente `Button` puede ser utilizado para crear un componente `ButtonGroup` de la siguiente manera:

```
---
import Button from './Button.astro';
---
<div>
  <Button title="Boton 1" />
  <Button title="Boton 2" />
  <Button title="Boton 3" />
</div>
```

#### Script de un componente <a href="#script-de-un-componente" id="script-de-un-componente"></a>

[Section titled Script de un componente](https://docs.astro.build/es/core-concepts/astro-components/#script-de-un-componente)

Astro utiliza una valla de código (`---`) para identificar el script del componente Astro. Si has escrito Markdown anteriormente deberías estar familiarizado con un concepto similar llamado _frontmatter_. El script del componente de Astro fue inspirado por este concepto.

Puedes utilizar el script del componente para escribir cualquier código de JavaScript que necesites para renderizar el maquetado. Esto puede incluir:

* Importar otros componentes Astro
* Importar componentes de otros frameworks, como React
* Importar datos, como un archivo JSON
* Consultar contenido de una API o base de datos
* Crear variables que luego puedes referenciar en tu maquetado

```
---
import UnComponenteAstro from '../components/UnComponenteAstro.astro';
import UnComponenteReact from '../components/UnComponenteReact.jsx';
import algunosDatos from '../data/pokemon.json';

// Acceder a props recibidas, por ejemplo `<X title="Hola Mundo" />`
const {title} = Astro.props;
// Consultar datos externos, de una API privada o base de datos
const datos = await fetch('API_URL_SECRETA/users').then(r => r.json());
---
<!-- ¡Tu maquetado va aquí! -->
```

La valla de código está diseñada para garantizar que el código JavaScript que escribes adentro se encuentre “encapsulado”. Este código no se filtrará a tu aplicación, o llegará al usuario final. Puedes escribir código que sea costoso o sensible (como una llamada a la base de datos) sin preocuparte por que estos datos sensibles lleguen al navegador del usuario.

&#x20;SUGERENCIA

¡Incluso puedes escribir TypeScript en el script del componente!

#### Maquetado del componente <a href="#maquetado-del-componente" id="maquetado-del-componente"></a>

[Section titled Maquetado del componente](https://docs.astro.build/es/core-concepts/astro-components/#maquetado-del-componente)

Debajo del script del componente vive el maquetado. El maquetado del componente define el HTML que generará tu componente.

Si escribes solo HTML en esta sección, el componente va a renderizar este HTML en cualquier página Astro donde sea importado o utilizado.

Sin embargo, la sintaxis de maquetado del componente de Astro también es compatible con **expresiones de JavaScript**, **componentes importados** y [**directivas especiales de Astro**](https://docs.astro.build/es/reference/directives-reference/). Los datos y valores definidos (en la construcción la página) en el script del componente pueden ser utilizados en el maquetado del componente para producir HTML creado dinámicamente.

```
---
// El script de tu componente va aquí!
import ReactPokemonComponent from '../components/ReactPokemonComponent.jsx';
const misPokemonesFavoritos = [/* ... */];
---
<!-- ¡Soporta comentarios HTML! -->

<h1>¡Hola mundo!</h1>

<!-- Utiliza props y otras variables definidas en el script del componente: -->
<p>Mi Pokémon favorito es: {Astro.props.title}</p>

<!-- Incluye otros componentes con la directiva de hidratación `client:`: -->
<ReactPokemonComponent client:visible />

<!-- Puedes mezclar HTML con expresiones de JavaScript, similar a JSX: -->
<ul>
  {misPokemonesFavoritos.map((data) => <li>{data.name}</li>)}
</ul>

<!-- ¡Use una directiva de maquetado para crear nombres de clase a partir de múltiples strings o incluso objetos! -->
<p class:list={["agregar", "dinámico", {classNames: true}]} />
```

### Expresiones similares a JSX <a href="#expresiones-similares-a-jsx" id="expresiones-similares-a-jsx"></a>

[Section titled Expresiones similares a JSX](https://docs.astro.build/es/core-concepts/astro-components/#expresiones-similares-a-jsx)

Puedes definir variables locales de JavaScript dentro del script del componente de Astro. ¡Luego puedes inyectar estas variables en el maquetado del componente usando expresiones similares a JSX!

&#x20;DINÁMICO VS REACTIVO

Usando este enfoque, puedes incluir valores _**dinámicos**_ que son calculados en el _frontmatter_. Sin embargo, una vez incluidos, estos valores no son _**reactivos**_ por lo que nunca cambiarán. Los componentes Astro son maquetados que solo son ejecutados una vez, en la construcción de la página.

Lee abajo para más ejemplos sobre las [diferencias entre Astro y JSX](https://docs.astro.build/es/core-concepts/astro-components/#diferencias-entre-astro-y-jsx)

#### Variables <a href="#variables" id="variables"></a>

[Section titled Variables](https://docs.astro.build/es/core-concepts/astro-components/#variables)

Las variables locales pueden ser agregadas al maquetado usando la sintaxis de llaves:

```
---
const nombre = "Astro";
---
<div>
  <h1>¡Hola {nombre}!</h1> <!-- <h1>¡Hola Astro!</h1> -->
</div>
```

#### Atributos dinámicos <a href="#atributos-dinamicos" id="atributos-dinamicos"></a>

[Section titled Atributos dinámicos](https://docs.astro.build/es/core-concepts/astro-components/#atributos-din%C3%A1micos)

Las variables locales pueden ser utilizadas entre llaves para pasar valores a atributos de componentes y elementos HTML:

```
---
const nombre = "Astro";
---
<h1 class={nombre}>Soporta expresiones en atributos</h1>

<MiComponente nombreDeAtributo={`MiNombreEs${nombre}`} />
```

&#x20;PRECAUCIÓN

Los atributos HTML se convierten en strings, debido a eso no es posible pasar funciones y objetos a elementos HTML. Por ejemplo, no puedes asignar una función manejadora de evento a un elemento HTML en un componente de Astro:

```
---
function handleClick () {
    console.log("¡botón clickeado!");
}
---
<!-- ❌ ¡Esto no funcionará! ❌ -->
<button onClick={handleClick}>¡No va a pasar nada si me clickeas!</button>
```

En vez de eso, utiliza un script del lado del cliente para agregar la función manejadora de evento, al igual que harías con Javascript vanilla:

```
---
---
<button id="button">Hazme click</button>
<script>
  function handleClick () {
    console.log("¡botón clickeado!");
  }
  document.getElementById("button").addEventListener("click", handleClick);
</script>
```

#### HTML dinámico <a href="#html-dinamico" id="html-dinamico"></a>

[Section titled HTML dinámico](https://docs.astro.build/es/core-concepts/astro-components/#html-din%C3%A1mico)

Las variables locales pueden ser utilizadas en funciones similares a JSX para producir elementos HTML dinámicos:

```
---
const items = ["Perro", "Gato", "Mono"];
---
<ul>
  {items.map((item) => (
    <li>{item}</li>
  ))}
</ul>
```

Astro puede mostrar HTML de forma condicional utilizando operadores lógicos y expresiones ternarias en JSX.

```
---
const visible = true;
---
{visible && <p>¡Muéstrame!</p>}

{visible ? <p>¡Muéstrame!</p> : <p>¡O muéstrame a mi!</p>}
```

#### Etiquetas dinámicas <a href="#etiquetas-dinamicas" id="etiquetas-dinamicas"></a>

[Section titled Etiquetas dinámicas](https://docs.astro.build/es/core-concepts/astro-components/#etiquetas-din%C3%A1micas)

También puedes usar etiquetas dinámicas para asignar a una variable el nombre de una etiqueta HTML o un componente importado.

```
---
import MyComponent from "./MyComponent.astro";
const Element = 'div'
const Component = MyComponent;
---
<Element>¡Hola!</Element> <!-- es renderizado como <div>¡Hola!</div> -->
<Component /> <!-- es renderizado como <MyComponent /> -->
```

Al usar etiquetas dinámicas:

**Los nombres de las variables deben estar en mayúscula**. Por ejemplo, usar `Element`, no `element`. De lo contrario, Astro intentará renderizar el nombre de la variable como una etiqueta literal de HTML.

**No admiten directivas de hidratación**. Al usar [`client:*` directiva de hidratación](https://docs.astro.build/es/core-concepts/framework-components/#hidratando-componentes-interactivos), Astro necesita saber cuáles son los componentes que se deben empaquetar para producción, y el patrón de etiqueta dinámica previene que esto funcione.

#### Fragmentos & elementos múltiples <a href="#fragmentos-elementos-multiples" id="fragmentos-elementos-multiples"></a>

[Section titled Fragmentos \&amp; elementos múltiples](https://docs.astro.build/es/core-concepts/astro-components/#fragmentos--elementos-m%C3%BAltiples)

Una plantilla de componente de Astro puede renderizar múltiples elementos sin necesidad de envolver todo en un solo `<div>` o `<>`, a diferencia de JavaScript o JSX.

```
---
// Maquetado con múltiples elementos
---
<p>No es necesario envolver elementos en un solo elemento contenedor.</p>
<p>Astro es compatible con el uso de múltiples elementos en la raíz del maquetado</p>
```

Sin embargo, al utilizar las expresiones para crear elementos dinámicamente, debes envolver estos elementos dentro de un **Fragment** de la misma forma que lo harías utilizando JavaScript o JSX. Astro es compatible con el uso de `<Fragment> </Fragment>` o su abreviación `<> </>`.

```
---
const items = ["Perro", "Gato", "Mono"];
---
<ul>
  {items.map((item) => (
    <>
      <li>{item} Rojo</li>
      <li>{item} Azul</li>
      <li>{item} Verde</li>
    </>
  ))}
</ul>
```

Los fragmentos también pueden ser útiles para evitar envolver componentes al usar las directivas [`set:*`](https://docs.astro.build/es/reference/directives-reference/#sethtml), como en el siguiente ejemplo:

```
---
const htmlString = '<p>Contenido HTML sin procesar</p>';
---
<Fragment set:html={htmlString} />
```

#### Diferencias entre Astro y JSX <a href="#diferencias-entre-astro-y-jsx" id="diferencias-entre-astro-y-jsx"></a>

[Section titled Diferencias entre Astro y JSX](https://docs.astro.build/es/core-concepts/astro-components/#diferencias-entre-astro-y-jsx)

La sintaxis del componente Astro es un superconjunto de HTML. Fue diseñado para que resulte familiar para alguien con experiencia en HTML o JSX, pero hay un par de diferencias clave entre los archivos `.astro` y JSX.

**Atributos**

[Section titled Atributos](https://docs.astro.build/es/core-concepts/astro-components/#atributos)

En Astro, utiliza el formato estándar `kebab-case` para todos los atributos HTML en lugar del `camelCase` que se usa en JSX. Esto incluso funciona para `class`, que no es compatible con React.

```
<div className="box" dataValue="3" />
<div class="box" data-value="3" />
```

**Comentarios**

[Section titled Comentarios](https://docs.astro.build/es/core-concepts/astro-components/#comentarios)

En Astro, puedes usar comentarios HTML estándar o comentarios al estilo de JavaScript.

```
---
---
<!-- Los comentarios con sintaxis HTML son válidos en archivos .astro -->
{/* Los comentarios con sintaxis de JS también son válidos */}
```

&#x20;PRECAUCIÓN

Los comentarios de estilo HTML serán incluidos en el DOM del navegador, mientras que los de JS serán omitidos. Para dejar mensajes TODO u otras explicaciones solo para desarrollo, es probable que quieras utilizar los comentarios de estilo JavaScript.

### Props de componentes <a href="#props-de-componentes" id="props-de-componentes"></a>

[Section titled Props de componentes](https://docs.astro.build/es/core-concepts/astro-components/#props-de-componentes)

Un componente de Astro puede definir y aceptar props. Estas props estarán disponibles para ser utilizadas en el renderizado del maquetado HTML y además estarán disponibles en el script del componente de manera global dentro del objeto `Astro.props`.

Aquí vemos un ejemplo de un componente que recibe una prop `saludo` y otra `nombre`. Fíjate que las props a recibir están desestructuradas del objeto global `Astro.props`.

```
---
// Utilización: <GreetingHeadline saludo="Qué tal" nombre="Amiga" />
const { saludo, nombre } = Astro.props
---
<h2>{saludo}, {nombre}!</h2>
```

Este componente, cuando se importa y renderiza en otros componentes, layouts o páginas de Astro, se pueden pasar estas props como atributos:

```
---
import GreetingHeadline from './GreetingHeadline.astro';
const name = "Astro"
---
<h1>Greeting Card</h1>
<GreetingHeadline greeting="Hi" name={name} />
<p>I hope you have a wonderful day!</p>
```

También puedes definir props con TypeScript usando una interfaz de tipo `Props`. Astro recogerá automáticamente la interfaz `Props` en el frontmatter y dará advertencias/errores de tipo para tu proyecto. A estas propiedades también se les puede dar valores predeterminados cuando se desestructuran desde `Astro.props`.

```
---
interface Props {
  nombre: string;
  saludo?: string;
}

const { saludo = "Hola", nombre } = Astro.props;
---
<h2>{saludo}, {nombre}!</h2>
```

A los props de componentes se les pueden dar valores predeterminados para usar cuando no se proporciona ninguno.

```
---
const { greeting = "Hello", name = "Astronaut" } = Astro.props;
---
<h2>{greeting}, {name}!</h2>
```

### Slots <a href="#slots" id="slots"></a>

[Section titled Slots](https://docs.astro.build/es/core-concepts/astro-components/#slots)

El elemento `<slot />` es un espacio reservado para contenido HTML externo, permitiéndote inyectar (o ingresar en la “ranura”) elementos hijos provenientes de otros archivos en el maquetado de tu componente.

Por defecto, todos los elementos hijos que le sean enviados a un componente serán renderizados en su `<slot />`.

&#x20;NOTA

Diferente a _props_, que son atributos enviados a un componente Astro y disponibles para utilizar con `Astro.props`, los _slots_ renderizan elementos HTML hijos donde se lo indique.

```
---
import Header from './Header.astro';
import Logo from './Logo.astro';
import Footer from './Footer.astro';

const { titulo } = Astro.props
---
<div id="content-wrapper">
  <Header />
  <Logo />
  <h1>{titulo}</h1>
  <slot />  <!-- aquí van los hijos -->
  <Footer />
</div>
```

```
---
import Wrapper from '../components/Wrapper.astro';
---
<Wrapper titulo="Página de Fred">
  <h2>Todo sobre Fred</h2>
  <p>Aquí veremos cosas sobre Fred.</p>
</Wrapper>
```

Este patrón es la base de la plantilla de página de un componente de Astro: una página entera de contenido HTML puede ser “envuelta” con etiquetas `<Layout></Layout>` y enviadas al componente Layout para ser renderizada dentro de elementos comunes de la página.

#### Slots con nombre <a href="#slots-con-nombre" id="slots-con-nombre"></a>

[Section titled Slots con nombre](https://docs.astro.build/es/core-concepts/astro-components/#slots-con-nombre)

Un componente de Astro también puede tener slots con nombre. Esto te permite compartir elementos HTML únicamente con el nombre correspondiente al slot.

```
---
import Header from './Header.astro';
import Logo from './Logo.astro';
import Footer from './Footer.astro';

const { titulo } = Astro.props
---
<div id="content-wrapper">
  <Header />
  <slot name="after-header"/>  <!--  hijos con el atributo `slot="after-header"` van aquí -->
  <Logo />
  <h1>{titulo}</h1>
  <slot />  <!--  hijos sin `slot`, o con el atributo `slot="default"` van aquí -->
  <Footer />
  <slot name="after-footer"/>  <!--  hijos con el atributo `slot="after-footer"` van aquí -->
</div>
```

```
---
import Wrapper from '../components/Wrapper.astro';
---
<Wrapper titulo="Página de Fred">
  <img src="https://my.photo/fred.jpg" slot="after-header">
  <h2>Todo sobre Fred</h2>
  <p>Aquí veremos cosas sobre Fred.</p>
  <p slot="after-footer">Copyright 2022</p>
</Wrapper>
```

Utiliza un atributo `slot="mi-slot"` en el elemento hijo que quieras enviar junto con su `<slot name="mi-slot" />` emparejado en tu componente.

&#x20;SUGERENCIA

Los slots con nombre también se pueden pasar a [componentes de framework](https://docs.astro.build/es/core-concepts/framework-components/) en archivos Astro.

#### Contenido alternativo para slots <a href="#contenido-alternativo-para-slots" id="contenido-alternativo-para-slots"></a>

[Section titled Contenido alternativo para slots](https://docs.astro.build/es/core-concepts/astro-components/#contenido-alternativo-para-slots)

Los slots también pueden renderizar **contenido alternativo** en el caso que no reciban datos con `<slot />` para emparejar, sea slot con nombre o no.

```
---
import Header from './Header.astro';
import Logo from './Logo.astro';
import Footer from './Footer.astro';

const { titulo } = Astro.props
---
<div id="content-wrapper">
  <Header />
  <Logo />
  <h1>{titulo}</h1>
  <slot>
    <p>Este es mi contenido alternativo, si no hay ningún elemento pasado al slot</p>
  </slot>
  <Footer />
</div>
```

### Estilos CSS <a href="#estilos-css" id="estilos-css"></a>

[Section titled Estilos CSS](https://docs.astro.build/es/core-concepts/astro-components/#estilos-css)

Astro también soporta etiquetas de estilo CSS `<style>` dentro del maquetado del componente.

Pueden utilizarse para estilar los componentes y todas las reglas de estilo son encapsuladas en el componente para evitar conflictos de CSS en aplicaciones grandes.

```
---
// El script de tu componente va aquí!
---
<style>
  /* encapsulado en el componente, otros H1 en la página no estarán afectados */
  h1 { color: red }
</style>

<h1>Hola mundo!</h1>
```

&#x20;PRECAUCIÓN

Los estilos definidos aquí serán aplicados únicamente en el maquetado del componente. **No** se verán afectados los componentes hijos ni cualquier otro componente importado por defecto.

📚 Lee nuestra [guía de estilos](https://docs.astro.build/es/guides/styling/) para más información en cómo aplicar estilos.

### Scripts del lado del cliente <a href="#scripts-del-lado-del-cliente" id="scripts-del-lado-del-cliente"></a>

[Section titled Scripts del lado del cliente](https://docs.astro.build/es/core-concepts/astro-components/#scripts-del-lado-del-cliente)

Los componentes de Astro soportan agregar interactividad del lado del cliente usando etiquetas `<script>` estándar de HTML.

Los scripts pueden ser usados para agregar event listeners, enviar datos análiticos, reproducir animaciones y todo lo demás que JavaScript puede hacer en la web.

```
<button data-confetti-button>Celebrate!</button>

<script>
  // Importar módulos npm.
  import confetti from 'canvas-confetti';

  // Encuentra el componente DOM en la página.
  const buttons = document.querySelectorAll('[data-confetti-button]');

  // Agrega un event listener para activar confetti cuando un botón es clickeado.
  buttons.forEach((button) => {
    button.addEventListener('click', () => confetti());
  });
</script>
```

Para evitar agrupar el script, puedes usar el atributo `is:inline`.

```
<script is:inline>
  // Será renderizado en el HTML tal cual sea escrito!
  // El importado de ESM relativos al archivo no serán resueltos.
</script>
```

Por defecto, Astro procesa y empaqueta las etiquetas `<script>`, agregando soporte para importar módulos npm, TypeScript y más.

Vea nuestra [Guía de scripts del lado del cliente](https://docs.astro.build/es/guides/client-side-scripts/) para más detalles.

### Componentes HTML <a href="#componentes-html" id="componentes-html"></a>

[Section titled Componentes HTML](https://docs.astro.build/es/core-concepts/astro-components/#componentes-html)

Astro soporta importar y usar archivos `.html` como componentes o colocarlos dentro del subdirectorio `src/pages`. Es posible que quieras usar componentes HTML si estás reusando código de un sitio existente construido sin usar frameworks, o si quieres asegurarte que tu componente no tiene características dinámicas.

Los componentes HTML solo deben contener HTML válido, y por lo tanto le faltarán características claves de los componentes de Astro.

* Ellos no soportan el frontmatter, importaciones del lado del servidor, o expresiones dinámicas.
* Cualquier etiqueta `<script>` quedan sin agrupar, son tratados como si tuvieran `in:inline`
* Ellos solo pueden referenciar recursos que están en la carpeta [`public/`](https://docs.astro.build/es/guides/images/#public).

&#x20;NOTA

Un [elemento `<slot/>`](https://docs.astro.build/es/core-concepts/astro-components/#slots) dentro de un componente HTML trabajar como lo haría en un componente de Astro. En cambio, para poder usar el elemento [Componente Web HTML Slot](https://developer.mozilla.org/es/docs/Web/HTML/Element/slot) añade `is:inline` al elemento `slot`.

\
