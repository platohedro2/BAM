# Conceptos generales de CSS & Etiquetas básicas de CSS

## ¿Qué es el CSS?



Las hojas de estilo en cascada ([**CSS**](https://developer.mozilla.org/es/docs/Glossary/CSS), cascading style sheets) permiten crear páginas web atractivas. Pero ¿cómo funcionan realmente? En este artículo explicaremos qué es el CSS con un ejemplo de sintaxis sencillo y describiremos algunos términos clave sobre este lenguaje.

En el módulo [Introducción al HTML](https://developer.mozilla.org/es/docs/Learn/HTML/Introduction\_to\_HTML), exponemos qué es el HTML y cómo se usa para definir documentos destinados a leerse en un navegador web. Los títulos se verán más grandes que el texto y los párrafos empezarán en una línea nueva y habrá un espacio entre ellos. Los enlaces aparecerán en un color diferente y subrayados para distinguirlos del resto del texto. Vienen predeterminados por el navegador y, en la práctica, son estilos muy básicos que el navegador aplica al HTML para asegurarse, básicamente, de que sean legibles incluso si el autor de la página no especifica un estilo explícito.

Sin embargo, Internet sería un lugar muy aburrido si todas las páginas web se vieran así. Usando CSS se pueden controlar con precisión cómo se ven los elementos HTML en el navegador, que presentará para las etiquetas de marcado el diseño que cada uno desee.

### [¿Para qué sirve el CSS?](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/What\_is\_CSS#%C2%BFpara\_qu%C3%A9\_sirve\_el\_css) <a href="#para_que_sirve_el_css" id="para_que_sirve_el_css"></a>

Como hemos mencionado, el CSS es un lenguaje informático que especifica cómo se presentan los documentos a los usuarios: cómo se diseñan, compaginan, etc.

Un **documento** suele ser un archivo de texto estructurado con un lenguaje de marcado: [HTML](https://developer.mozilla.org/es/docs/Glossary/HTML) es el más común, pero también existen otros como [SVG](https://developer.mozilla.org/es/docs/Glossary/SVG) o [XML](https://developer.mozilla.org/es/docs/Glossary/XML).

**Presentar** un documento a un usuario significa convertirlo en un formulario que el público pueda utilizar. Los navegadores, como por ejemplo [Firefox](https://developer.mozilla.org/es/docs/Glossary/Mozilla\_Firefox), [Chrome](https://developer.mozilla.org/es/docs/Glossary/Google\_Chrome) o [Edge (en-US)](https://developer.mozilla.org/en-US/docs/Glossary/Microsoft\_Edge), están diseñados para presentar documentos visualmente en una pantalla de ordenador, un proyector o una impresora.

**Nota:** Un navegador también recibe el nombre de agente de usuario, que consiste en un programa informático que representa a una persona dentro del sistema. Los navegadores son el modelo principal de agente de usuario en el que pensamos cuando hablamos de CSS, pero no son el único. Hay otros documentos de usuario disponibles, como los que convierten documentos HTML y CSS en PDF para imprimir.

El CSS se puede usar para estilos de texto muy básicos como, por ejemplo, cambiar el [color](https://developer.mozilla.org/es/docs/Web/CSS/color\_value) y el [tamaño](https://developer.mozilla.org/es/docs/Web/CSS/font-size) de los encabezados y los enlaces. Se puede utilizar para crear un diseño, como podría ser [convertir una columna de texto en una composición (en-US)](https://developer.mozilla.org/en-US/docs/Web/CSS/Layout\_cookbook/Column\_layouts) con un área de contenido principal y una barra lateral para información relacionada. Incluso se puede usar para crear efectos de [animación](https://developer.mozilla.org/es/docs/Web/CSS/CSS\_Animations). Echa un vistazo a los enlaces de este párrafo para ver ejemplos específicos.

### [Sintaxis del CSS](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/What\_is\_CSS#sintaxis\_del\_css) <a href="#sintaxis_del_css" id="sintaxis_del_css"></a>

El CSS es un lenguaje basado en reglas: cada usuario define las reglas que especifican los grupos de estilos que van a aplicarse a elementos particulares o grupos de elementos de la página web. Por ejemplo: «Quiero que el encabezado principal de mi página se muestre en letras grandes de color rojo».

El código siguiente muestra una regla CSS muy simple que proporcionaría el estilo descrito en el párrafo anterior:

```
h1 {
    color: red;
    font-size: 5em;
}
```



La regla se abre con un [selector (en-US)](https://developer.mozilla.org/en-US/docs/Glossary/CSS\_Selector). Este _selecciona_ el elemento HTML que vamos a diseñar. En este caso, diseñaremos encabezados de nivel uno ([`<h1>` (en-US)](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading\_Elements)).

Luego tenemos un conjunto de llaves `{ }`. Entre estas habrá una o más **declaraciones**, que tomarán la forma de pares de **propiedad** y **valor**. Cada par especifica cada una de las propiedades de los elementos seleccionados y el valor que queremos dar a esa propiedad.

Antes de los dos puntos, tenemos la propiedad; y después, el valor. Las [propiedades (en-US)](https://developer.mozilla.org/en-US/docs/Glossary/property/CSS) CSS admiten diferentes valores, dependiendo de qué propiedad se esté especificando. En el ejemplo anterior, tenemos la propiedad `color`, que puede tomar varios [valores de color](https://developer.mozilla.org/es/docs/Learn/CSS/Building\_blocks/Values\_and\_units#color). También tenemos la propiedad de `font-size`, que puede tomar varias [unidades de tamaño](https://developer.mozilla.org/es/docs/Learn/CSS/Building\_blocks/Values\_and\_units#n%c3%bameros\_longitudes\_y\_porcentajes) como valor.

Una hoja de estilo CSS contendrá muchas de estas reglas, escritas una tras otra.

```
h1 {
    color: red;
    font-size: 5em;
}

p {
    color: black;
}
```



Algunos valores se aprenden rápidamente, mientras que otros deberán buscarse. Las páginas de propiedades individuales que hay en el proyecto MDN proporcionan una forma rápida de buscar propiedades y sus valores en caso de olvidarlos o desear saber qué más se puede usar como valor.

**Nota:** Puedes encontrar enlaces a todas las páginas de las propiedades CSS (junto con otras características CSS) enumeradas en la [referencia CSS](https://developer.mozilla.org/es/docs/Web/CSS/Reference) del proyecto MDN. Alternativamente, deberías acostumbrarte a buscar «mdn _css-feature-name_» en tu motor de búsqueda favorito siempre que necesites obtener más información sobre una función CSS. Por ejemplo, intenta buscar «mdn color» y «mdn font-size».

### [Módulos CSS](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/What\_is\_CSS#m%C3%B3dulos\_css) <a href="#modulos_css" id="modulos_css"></a>

Como hay tantas cosas que se podrían diseñar usando CSS, el lenguaje se divide en _módulos_. Verás referencias a estos módulos a medida que explores en MDN y observarás que muchas de las páginas de documentación están organizadas en torno a un módulo en particular. Por ejemplo, puedes echar un vistazo a la referencia MDN del módulo [Fondos y bordes](https://developer.mozilla.org/es/docs/Web/CSS/CSS\_Backgrounds\_and\_Borders) para averiguar cuál es su propósito, qué otras propiedades y características diferentes contiene. También encontrarás enlaces a la _especificación CSS_ que define la tecnología (ver más abajo).

En esta fase, no debes preocuparte demasiado sobre cómo se estructura el CSS, sin embargo, puede facilitarte la búsqueda de información si, por ejemplo, sabes que es probable que cierta propiedad se encuentre entre otras similares y, por lo tanto, en la misma especificación.

Volvamos al módulo de Fondos y bordes para un ejemplo específico: puedes pensar que tiene lógica que las propiedades [`background-color`](https://developer.mozilla.org/es/docs/Web/CSS/background-color) y [`border-color`](https://developer.mozilla.org/es/docs/Web/CSS/border-color) se definan en este módulo. Y llevas toda la razón.

#### [Especificaciones CSS](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/What\_is\_CSS#especificaciones\_css) <a href="#especificaciones_css" id="especificaciones_css"></a>

Todas las tecnologías de estándares web (HTML, CSS, JavaScript, etc.) se definen en extensos documentos denominados especificaciones, publicados por organizaciones de estándares (como [W3C (en-US)](https://developer.mozilla.org/en-US/docs/Glossary/W3C), [WHATWG](https://developer.mozilla.org/es/docs/Glossary/WHATWG), [ECMA (en-US)](https://developer.mozilla.org/en-US/docs/Glossary/ECMA) o [Khronos (en-US)](https://developer.mozilla.org/en-US/docs/Glossary/Khronos)) que definen con precisión cómo se supone que deben comportarse esas tecnologías.

El caso de CSS no es diferente: lo desarrolla un grupo del W3C llamado [CSS Working Group](https://www.w3.org/Style/CSS/). Este grupo está compuesto por representantes de proveedores de navegadores y otras compañías interesadas en CSS. También hay otras personas, conocidas como _expertos invitados_, que actúan como voces independientes y no están vinculados a ninguna organización.

El CSS Working Group desarrolla o especifica características nuevas del CSS. Algunas veces lo hacen porque un navegador en particular está interesado en alguna capacidad, otras porque los diseñadores y desarrolladores web piden una característica, y otras porque el grupo ha identificado un requisito. El CSS está en desarrollo constante y todos los días presenta nuevas características disponibles. Sin embargo, un elemento clave sobre el CSS es que toda la comunidad se esfuerza mucho en no cambiar nunca nada que pueda perjudicar los sitios web antiguos. ¡Un sitio web creado en el año 2000, que utiliza el poco CSS disponible que había en ese momento, aún debería poder utilizarse hoy en día!

Como recién llegado al CSS, es probable que encuentres las especificaciones abrumadoras: están destinadas a que los ingenieros las utilicen para implementar soporte de sus características en los agentes de usuario en que trabajan, no para que lo lean los desarrolladores web para comprender el CSS. Muchos desarrolladores experimentados preferirán consultar la documentación disponible en MDN u otros tutoriales. Sin embargo, vale la pena saber que existen y comprender la relación que hay entre el CSS que estás utilizando, el soporte del navegador (ver más abajo) y las especificaciones.

### [Soporte del navegador](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/What\_is\_CSS#soporte\_del\_navegador) <a href="#soporte_del_navegador" id="soporte_del_navegador"></a>

[Report problems with this compatibility data on GitHub](https://github.com/mdn/browser-compat-data/issues/new?mdn-url=https%3A%2F%2Fdeveloper.mozilla.org%2Fes%2Fdocs%2FLearn%2FCSS%2FFirst\_steps%2FWhat\_is\_CSS\&metadata=%3C%21--+Do+not+make+changes+below+this+line+--%3E%0A%3Cdetails%3E%0A%3Csummary%3EMDN+page+report+details%3C%2Fsummary%3E%0A%0A\*+Query%3A+%60css.properties.font-family%60%0A\*+Report+started%3A+2022-11-29T21%3A15%3A27.363Z%0A%0A%3C%2Fdetails%3E\&title=css.properties.font-family+-+%3CSUMMARIZE+THE+PROBLEM%3E\&template=data-problem.yml)

#### Legend <a href="#legend" id="legend"></a>

Tip: you can click/tap on a cell for more information.

Full supportFull supportNo supportNo supportExperimental. Expect behavior to change in the future.See implementation notes.User must explicitly enable this feature.Uses a non-standard name.Has more compatibility info.

Una vez se ha especificado el CSS, solo es útil en el desarrollo de páginas web si uno o más navegadores lo han implementado. Esto significa que el código se ha escrito para convertir las instrucciones que se especifican en nuestro archivo CSS en algo que se pueda mostrar en pantalla. Veremos este proceso más en profundidad en el artículo [Cómo funciona el CSS](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works). Es inusual que todos los navegadores puedan implementar una misma característica al mismo tiempo, por lo que suele haber una brecha en la que se pueden usar algunas partes del CSS en algunos navegadores pero no en otros. Por este motivo, es útil poder verificar el estado de implementación. En cada una de las páginas de propiedades que hay en la MDN se puede ver el estado de la propiedad de interés, por lo que se puede saber si será posible utilizarla en un sitio web.

Lo que sigue es el gráfico de datos de compatibilidad para la propiedad CSS [`font-family`](https://developer.mozilla.org/es/docs/Web/CSS/font-family).



En este artículo aplicaremos CSS a un documento HTML sencillo para aprender algunos elementos prácticos sobre este lenguaje.

### [Empezamos con algo de HTML](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#empezamos\_con\_algo\_de\_html) <a href="#empezamos_con_algo_de_html" id="empezamos_con_algo_de_html"></a>

Nuestro punto de partida es un documento HTML. Puedes copiar el código de abajo si quieres trabajar en tu ordenador. Guarda el siguiente código como `index.html` en una carpeta de tu equipo.

```
<!doctype html>
<html lang="es">
<head>
    <meta charset="utf-8">
    <title>Empezamos con el CSS</title>
</head>

<body>

    <h1>Soy un título de nivel uno</h1>

    <p>Este es un párrafo de texto. En el texto hay un <span>elemento span</span>
y también un <a href="http://example.com">enlace</a>.</p>

    <p>Este es el segundo párrafo. Contiene un elemento <em>destacado</em>.</p>

    <ul>
        <li>Punto uno</li>
        <li>Punto dos</li>
        <li>Punto <em>tres</em></li>
    </ul>

</body>

</html>
```



**Nota:** Si lees esto en un dispositivo o un entorno donde no puedes crear archivos fácilmente, no te preocupes. A continuación hay editores de código en vivo que van a permitirte escribir ejemplos de código en esta misma página.

### [Agregar CSS a un documento](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#agregar\_css\_a\_un\_documento) <a href="#agregar_css_a_un_documento" id="agregar_css_a_un_documento"></a>

Lo primero que se debe hacer es decirle al documento HTML que hay algunas reglas CSS que queremos que use. Hay tres formas diferentes de aplicar CSS a un documento HTML, sin embargo, por ahora, veremos la forma más habitual y útil de hacerlo: vincular el CSS desde el encabezado del documento.

Crea un archivo en la misma carpeta que tu documento HTML y guárdalo como `styles.css`. La extensión `.css` muestra que es un archivo CSS.

Para vincular `styles.css` a `index.html`, añade la siguiente línea en algún lugar dentro del [`<head>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/head) del documento HTML:

```
<link rel="stylesheet" href="styles.css">
```



Este elemento [`<link>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/link) le dice al navegador que hay una hoja de estilo con el atributo `rel` y la ubicación de esa hoja de estilo como el valor del atributo `href`. Puedes probar si el CSS funciona añadiendo una regla a `styles.css`. Usando el editor de código, añade lo siguiente al archivo CSS:

```
h1 {
  color: red;
}
```



Guarda los archivos HTML y CSS antes de volver a cargar la página en un navegador web. Ahora el título de nivel uno de la parte superior del documento debería ser rojo. Si esto sucede, ¡felicidades!: has aplicado correctamente un poco de CSS a un documento HTML. Si no lo hace, verifica que hayas escrito todo correctamente.

Puedes continuar trabajando en `styles.css` localmente o usar nuestro editor interactivo para continuar con este tutorial. El editor interactivo actúa como si el CSS del primer panel estuviera vinculado al documento HTML, tal como lo hemos hecho con el documento anterior.

### [Dar formato a elementos HTML](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#dar\_formato\_a\_elementos\_html) <a href="#dar_formato_a_elementos_html" id="dar_formato_a_elementos_html"></a>

Al poner nuestro título de encabezado en rojo, ya hemos demostrado que podemos elegir un elemento HTML y darle formato. Hacemos esto con un _selector de elementos_: un selector que coincide directamente con el nombre de un elemento HTML. Para determinar todos los párrafos del documento, se usa el selector `p`. Para hacer que todos los párrafos se vean verdes se usa:

```
p {
  color: green;
}
```



Puedes determinar múltiples selectores a la vez, separándolos con una coma. Si queremos que todos los párrafos y todos los elementos de la lista sean verdes, el código se verá así:

```
p, li {
    color: green;
}
```



Pruébalo en el editor interactivo que encontrarás a continuación (edita los cuadros de código) o en tu documento CSS.

### [Cambiar el comportamiento predeterminado de los elementos](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#cambiar\_el\_comportamiento\_predeterminado\_de\_los\_elementos) <a href="#cambiar_el_comportamiento_predeterminado_de_los_elementos" id="cambiar_el_comportamiento_predeterminado_de_los_elementos"></a>

Cuando miramos un documento HTML bien marcado, incluso con algo tan simple como nuestro ejemplo, podemos ver que el navegador facilita la legibilidad de este documento HTML al añadir un estilo predeterminado. Los títulos se muestran grandes y en negrita, y la lista tiene viñetas. Esto sucede porque los navegadores tienen hojas de estilo internas que contienen estilos predeterminados, los cuales se aplican a todas las páginas por defecto. Sin ellos, todo el texto se uniría en un grupo y tendríamos que darle formato desde cero. Todos los navegadores modernos muestran el contenido HTML por defecto de la misma manera.

Sin embargo, a menudo querrás algo diferente a la elección que ha hecho el navegador. Esto se puede solucionar con el simple hecho de escoger el elemento HTML que deseas cambiar y utilizar una regla CSS para cambiar su apariencia. Un buen ejemplo es `<ul>`, que muestra una lista desordenada. Tiene viñetas y, si decidimos que no las queremos, podemos eliminarlas de este modo:

```
li {
  list-style-type: none;
}
```



Ahora, intenta añadir esto a tu CSS.

Es muy conveniente consultar en MDN la propiedad `list-style-type` para ver qué valores admite. Echa un vistazo a la página de [`list-style-type`](https://developer.mozilla.org/es/docs/Web/CSS/list-style-type) y encontrarás un ejemplo interactivo en la parte superior para probar diferentes valores (todos los permitidos se detallan más abajo en esa misma página).

Al mirar esa página, descubrirás que, además de eliminar las viñetas de la lista, también puedes cambiarlas. Intenta cambiarlas por unas cuadradas utilizando el valor `square`.

### [Añadir una clase](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#a%C3%B1adir\_una\_clase) <a href="#anadir_una_clase" id="anadir_una_clase"></a>

Hasta ahora, hemos utilizado elementos cuyo nombre se basa en el nombre de elemento que reciben en HTML. Esto funciona siempre que se desee que todos los elementos de ese tipo tengan el mismo aspecto en el documento. La mayoría de las veces no es el caso, por lo que deberás encontrar una manera de seleccionar un subconjunto de los elementos sin que cambien los demás. La forma más común de hacer esto es añadir una clase al elemento HTML y determinarla.

En tu documento HTML, añade al segundo elemento de la lista un [atributo de clase](https://developer.mozilla.org/es/docs/Web/HTML/Global\_attributes/class). Debería verse así:

```
<ul>
  <li>Punto uno</li>
  <li class = "special">Punto dos</li>
  <li>Punto <em>tres</em></li>
</ul>
```



En tu CSS, puedes seleccionar una clase `special` creando un selector que comience con un carácter de punto final. Añade lo siguiente a tu archivo CSS:

```
.special {
  color: orange;
  font-weight: bold;
}
```



Guarda y actualiza para ver cuál es el resultado.

Puedes aplicar la clase `special` a cualquier elemento de la página que desees que tenga el mismo aspecto que este elemento de lista. Por ejemplo, es posible que desees que el `<span>` del párrafo también sea naranja y en negrita. Intenta añadirle una `class` `special`, luego vuelve a cargar la página y observa qué sucede.

A veces verás reglas con un selector que enumera el selector de elementos HTML junto con la clase:

```
li.special {
  color: orange;
  font-weight: bold;
}
```



Esta sintaxis significa «determina cualquier elemento `li` que tenga una clase special». Si hicieras esto, ya no podrías aplicar la clase a un elemento `<span>` u otro elemento simplemente añadiéndole la clase; tendrías que añadir ese elemento a la lista de selectores:

```
li.special,
span.special {
  color: orange;
  font-weight: bold;
}
```



Como puedes imaginar, algunas clases pueden aplicarse a muchos elementos y no queremos tener que seguir editando el CSS cada vez que algo nuevo necesita adoptar ese estilo. Por lo tanto, a veces es mejor eludir el elemento y simplemente referirse a la clase, a menos que sepas que vas a querer crear algunas reglas especiales para un solo elemento y tal vez quieras asegurarte de que no se apliquen a otros elementos.

### [Dar formato según la ubicación en un documento](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#dar\_formato\_seg%C3%BAn\_la\_ubicaci%C3%B3n\_en\_un\_documento) <a href="#dar_formato_segun_la_ubicacion_en_un_documento" id="dar_formato_segun_la_ubicacion_en_un_documento"></a>

Hay momentos en los que querrás que algo se vea diferente en función de dónde esté en el documento. Hay múltiples selectores que pueden hacerlo, pero por ahora veremos solo un par. En nuestro documento hay dos elementos `<em>`: uno dentro de un párrafo y el otro dentro de un elemento de la lista. Para seleccionar solo un `<em>` que esté anidado dentro de un elemento `<li>`, podemos usar un selector llamado **combinador descendente**, que simplemente toma la forma de un espacio entre otros dos selectores.

Añade la siguiente regla a la hoja de estilo.

```
li em {
  color: rebeccapurple;
}
```



Este selector separará cualquier elemento `<em>` que esté dentro de (un descendiente de) `<li>`. Entonces, en tu documento de ejemplo, deberías encontrar que el `<em>` del tercer elemento de la lista es morado, pero el que hay en el párrafo no ha cambiado.

Otra cosa que puedes probar es dar formato un párrafo que venga directamente a continuación de un título que esté en el mismo nivel de jerarquía en el HTML. Para hacerlo, coloca un `+` (un **combinador hermano adyacente**) entre los selectores.

Intenta añadir también esta regla a la hoja de estilo:

```
h1 + p {
  font-size: 200%;
}
```



El ejemplo que encontrarás a continuación incluye las dos reglas anteriores. Intenta añadir una regla para que un `span` dentro de un párrafo se vuelva rojo. Sabrás si lo has hecho bien si el `<span>` en el primer párrafo se vuelve rojo pero el que hay en el primer elemento de la lista no cambia de color.

**Nota:** Como puedes ver, el CSS nos ofrece varias formas de seleccionar elementos, y hasta ahora solo hemos arañado la superficie. Examinaremos todos estos selectores y muchos más en los artículos correspondientes a [Selectores](https://developer.mozilla.org/es/docs/Learn/CSS/Building\_blocks/Selectors) que encontrarás más adelante.

### [Dar formato según el estado](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#dar\_formato\_seg%C3%BAn\_el\_estado) <a href="#dar_formato_segun_el_estado" id="dar_formato_segun_el_estado"></a>

El último tipo de estilo que veremos en este tutorial es la capacidad de dar formato a los elementos en función de su estado. Un ejemplo sencillo es el estilo de los enlaces. Cuando damos formato a un enlace, necesitamos seleccionar el elemento [`<a>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/a) (anclaje). Tiene diferentes estados dependiendo de si se ha visitado o no, se pasa por encima, o se presiona con el teclado o se hace clic (se activa). Puedes usar CSS para dar formato a estos diferentes estados. El CSS que encontrarás a continuación presenta en color rosa los enlaces que no se han visitado y en verde los que sí.

```
a:link {
  color: pink;
}

a:visited {
  color: green;
}
```



Puedes cambiar la apariencia del enlace, por ejemplo, eliminando el subrayado, lo que se logra mediante la siguiente regla:

```
a:hover {
  text-decoration: none;
}
```



En el ejemplo que encontrarás a continuación, puedes jugar con diferentes valores para los distintos estados de un enlace. Hemos añadido las reglas anteriores y ahora nos damos cuenta de que el color rosa es demasiado claro y difícil de leer, ¿por qué no cambiarlo a otro que se vea mejor? ¿Puedes poner los enlaces en negrita?

Hemos eliminado el subrayado del enlace cuando el ratón se pasa por encima, y se puede eliminar de todos los estados de un enlace. Sin embargo, vale la pena recordar que en una página web real deberás asegurarte de que los visitantes sepan reconocer que se trata de un enlace. Que aparezca subrayado puede ser una pista importante para que las personas se den cuenta de que pueden hacer clic en una palabra dentro del párrafo, ya que es a lo que están acostumbrados. Al igual que con todo en CSS, existe la posibilidad de que tus cambios resten accesibilidad al documento. Intentaremos resaltar estas posibles dificultades en los lugares apropiados.

**Nota:** a menudo verás que se menciona la [accesibilidad](https://developer.mozilla.org/es/docs/Learn/Accessibility) en estas lecciones y en MDN. Cuando hablamos de accesibilidad nos referimos al requisito de que nuestras páginas web sean comprensibles y usables para todas las personas.

Puede que tu visitante acceda a la página desde un ordenador con ratón o trackpad, o un teléfono inteligente con pantalla táctil. O puede que use un lector de pantalla que lea el contenido del documento, así como puede que necesite un tamaño de texto más grande o navegar por la página usando solo el teclado.

Un documento HTML simple es, generalmente, accesible para todos. Es importante que el documento no pierda accesibilidad a medida que vayas aplicándole estilo.

### [Combinaciones de selectores y combinadores](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#combinaciones\_de\_selectores\_y\_combinadores) <a href="#combinaciones_de_selectores_y_combinadores" id="combinaciones_de_selectores_y_combinadores"></a>

Vale la pena señalar que puedes hacer múltiples combinaciones de selectores y combinadores. Por ejemplo:

```
/* selecciona cualquier elemento <span> que se encuentre dentro de un <p>, que esté dentro de un <artículo> */
artículo p span { ... }

/* selecciona cualquier <p> que se encuentre directamente después de <ul>, que va directamente después de <h1> */
h1 + ul + p { ... }
```



También puedes combinar varios tipos juntos. Intenta añadir lo siguiente al código:

```
body h1 + p .special {
  color: yellow;
  background-color: black;
  padding: 5px;
}
```



Dará formato a cualquier elemento con la clase `special`, dentro de un elemento `<p>` que venga justo después de `<h1>`, el cual se encuentra dentro de `<body>`. ¡Uf!

En el HTML original que proporcionamos, el único elemento al que esto aplica estilo es `<span class="special">`.

No te preocupes si ahora mismo te parece complicado: irás acostumbrarte a medida que escribas más CSS.

### [Para terminar](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started#para\_terminar) <a href="#para_terminar" id="para_terminar"></a>

En este tutorial, hemos visto varias formas con las que se puede diseñar un documento usando CSS. Desarrollaremos este conocimiento a medida que avancemos con el resto de las lecciones. Sin embargo, ahora ya sabes lo suficiente como para aplicar estilo al texto, aplicar CSS en función de diferentes formas de determinar elementos en el documento y buscar propiedades y valores en la documentación de MDN.

\
Cómo se estructura el CSS

* [Anterior](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started)
* [Overview: First steps](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps)
* [Siguiente](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works)

Ahora que ya sabes qué es el CSS y conoces sus conceptos básicos, es hora de profundizar un poco más en la estructura del lenguaje en sí. Ya hemos visto muchos de los conceptos que aparecen en este artículo; puedes volver para recapitular si más adelante encuentras conceptos confusos.

### [Aplicar CSS al HTML](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#aplicar\_css\_al\_html) <a href="#aplicar_css_al_html" id="aplicar_css_al_html"></a>

Lo primero que veremos son los tres métodos para aplicar CSS a un documento.

#### [Hoja de estilo externa](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#hoja\_de\_estilo\_externa) <a href="#hoja_de_estilo_externa" id="hoja_de_estilo_externa"></a>

En [Empezar con el CSS](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started), vinculamos una hoja de estilo externa a nuestra página. Este es el método más común y útil para adjuntar CSS a un documento, porque puedes vincular el CSS a varias páginas y dar estilo a todas ellas con la misma hoja de estilo. En la mayoría de los casos, las diferentes páginas de un sitio web se verán más o menos iguales, de modo que puedes usar el mismo conjunto de reglas para el aspecto y la interacción básicos.

Una hoja de estilo externa significa que el CSS está escrito en un archivo independiente con una extensión `.css` y que lo vinculas desde un elemento `<link>` de HTML:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Mi experimento CSS</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>
    <h1>¡Hola, mundo!</h1>
    <p>Este es mi primer ejemplo de CSS</p>
  </body>
</html>
```



El archivo CSS podría parecerse a esto:

```
h1 {
  color: blue;
  background-color: yellow;
  border: 1px solid black;
}

p {
  color: red;
}
```



El atributo `href` del elemento [`<link>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/link) tiene que hacer referencia a un archivo de tu sistema de archivos.

En el ejemplo anterior, el archivo CSS está en la misma carpeta que el documento HTML, pero puedes colocarlo en otro lugar y especificar la ruta adecuada. Por ejemplo:

```
<!-- Dentro de un subdirectorio llamado styles dentro del directorio de trabajo -->
<link rel="stylesheet" href="styles/style.css">

<!-- Dentro de un subdirectorio llamado general, que está en un subdirectorio llamado styles, dentro del directorio de trabajo -->
<link rel="stylesheet" href="styles/general/style.css">

<!-- Sube un nivel de directorio, y luego dentro de un subdirectorio llamado styles -->
<link rel="stylesheet" href="../styles/style.css">
```



#### [Hoja de estilo interna](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#hoja\_de\_estilo\_interna) <a href="#hoja_de_estilo_interna" id="hoja_de_estilo_interna"></a>

Una hoja de estilo interna es cuando no hay ningún archivo CSS externo, sino que colocas tu CSS dentro de un elemento [`<style>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/style) contenido dentro del elemento [`<head>`](https://developer.mozilla.org/es/docs/Web/HTML/Element/head) del HTML.

En este caso, el HTML se vería así:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Mi experimento CSS</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }

      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>¡Hola, mundo!</h1>
    <p>Este es mi primer ejemplo de CSS</p>
  </body>
</html>
```



Esto puede ser útil en algunas circunstancias (tal vez estés trabajando con un sistema de administración de contenido donde no sea posible modificar los archivos CSS directamente), pero no es tan eficiente como las hojas de estilo externas: en una página web, deberías repetir el CSS en cada página y actualizarlo en varios lugares en caso de que hubiera que hacer cambios.

#### [Estilos en línea](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#estilos\_en\_l%C3%ADnea) <a href="#estilos_en_linea" id="estilos_en_linea"></a>

Los estilos en línea son declaraciones CSS que afectan a un solo elemento, contenido dentro de un atributo de `style`:

```
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>Mi experimento CSS</title>
  </head>
  <body>
    <h1 style="color: blue;background-color: yellow;border: 1px solid black;">¡Hola mundo!</h1>
    <p style="color:red;">Este es mi primer ejemplo de CSS</p>
  </body>
</html>
```



**¡No hagas esto a menos que realmente tengas que hacerlo!** Es realmente malo a la hora de realizar el mantenimiento (puede que tengas que actualizar la misma información varias veces en un mismo documento), y además mezcla tu información CSS para la presentación con tu información HTML para la estructura, lo que dificulta la lectura y la comprensión del código. Mantener los diferentes tipos de código separados facilita trabajar con ellos.

Hay ciertos lugares donde los estilos en línea son más comunes, o incluso aconsejables. Es posible que tengas que recurrir a ellos si realmente tu entorno de trabajo es restrictivo (tal vez el CMS solo te permita editar el cuerpo del HTML). También verás que se usan mucho en el correo electrónico en formato HTML para lograr la máxima compatibilidad con el mayor número de clientes.

### [Juguemos con el CSS de este artículo](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#juguemos\_con\_el\_css\_de\_este\_art%C3%ADculo) <a href="#juguemos_con_el_css_de_este_articulo" id="juguemos_con_el_css_de_este_articulo"></a>

En este artículo hay mucho CSS con el que jugar. Para hacerlo, recomendamos crear un nuevo directorio/carpeta en el ordenador, dentro de la cual deberás crear una copia de los siguientes dos archivos:

**index.html:**

```
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Mis experimentos CSS</title>
    <link rel="stylesheet" href="styles.css">
  </head>
  <body>

    <p>Crea tu HTML de prueba aquí</p>

  </body>
</html>
```



**styles.css:**

```
/* Crea tu CSS de prueba aquí */

p {
  color: red;
}
```



Entonces, cuando te encuentres con un CSS con el que desees experimentar, reemplaza el contenido `<body>` del HTML con algo de HTML sin estilos y añade CSS a tu archivo de CSS para darle estilo.

Si no estás en un sistema donde puedas crear archivos fácilmente, puedes utilizar el editor interactivo que encontrarás a continuación para experimentar.

¡Sigue leyendo y disfruta!

### [Selectores](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#selectores) <a href="#selectores" id="selectores"></a>

No se puede hablar de CSS sin mencionar los selectores, de los cuales ya hemos descubierto varios tipos diferentes en la lección [Empezar con el CSS](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Getting\_started). Un selector es, como determinamos, un elemento de nuestro documento HTML para aplicarle estilo. Si los estilos no se aplican correctamente, es probable que el selector no coincida con lo que crees que debería coincidir.

Cada regla CSS comienza con un selector o una lista de selectores que indican al navegador a qué elemento o elementos deben aplicarse dichas reglas. Todos los siguientes son ejemplos de selectores válidos o listas de selectores.

```
h1
a:link
.manythings
#onething
*
.box p
.box p:first-child
h1, h2, .intro
```



**Prueba a crear algunas reglas CSS que usen los selectores anteriores y algo de HTML sin estilos. Si no conoces alguna de las sintaxis anteriores, ¡prueba a buscarla en MDN!**

**Nota:** Aprenderás mucho más sobre los selectores en nuestros tutoriales sobre [selectores CSS](https://developer.mozilla.org/es/docs/Learn/CSS/Building\_blocks/Selectors) de la próxima lección.

#### [Especificidad](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#especificidad) <a href="#especificidad" id="especificidad"></a>

A menudo habrá situaciones en las que dos selectores podrían determinar un mismo elemento HTML. Considera la siguiente hoja de estilo, en que definimos una regla con un selector `p` que establecerá los párrafos en color azul, y también una clase que establecerá los elementos seleccionados en color rojo.

```
.special {
  color: red;
}

p {
  color: blue;
}
```



Digamos que en nuestro documento HTML hay un párrafo con una clase `special`. Ambas reglas podrían aplicarse. ¿Cuál ganará? ¿De qué color crees que será nuestro párrafo?

```
<p class="special">¿De qué color soy?</p>
```



El lenguaje CSS tiene reglas para controlar cuál ganará en caso de colisión; reciben el nombre de **cascada** y **especificidad**. En el siguiente bloque de códigos hemos definido dos reglas para el selector `p`, pero el párrafo termina siendo de color azul. Esto se debe a que la declaración que lo establece en azul aparece más abajo en la hoja de estilo, y los estilos posteriores anulan a los anteriores. Así funciona la regla de la cascada.

```
p {
  color: red;
}

p {
  color: blue;
}
```

Copy to Clipboard

Sin embargo, en el caso de nuestro primer bloque, que contiene un selector de clase y otro de elementos, la clase ganará. Esto hará que el párrafo sea rojo, incluso aunque aparezca antes en la hoja de estilo. Una clase se describe de forma más específica o con más especificidad que el selector de elementos, razón por la que gana.

**Prueba el ejemplo anterior: añade el HTML a tu experimento, luego pon las dos reglas `p { ... }` a tu hoja de estilo. A continuación, cambia el primer selector `p` por `.special` para ver cómo cambia el estilo.**

Las reglas de especificidad y de cascada pueden parecer un poco complicadas al principio. Son más fáciles de entender a medida que se van adquiriendo conocimientos de CSS. En nuestro artículo sobre [Cascada y herencia](https://developer.mozilla.org/es/docs/Learn/CSS/Building\_blocks/Cascade\_and\_inheritance), que abordaremos en la próxima lección, se explicará en detalle, incluyendo cómo calcular la especificidad. Por ahora, solo has de saber que existe y que a veces el CSS no se aplica como esperas porque algo más en la hoja de estilo tiene una mayor especificidad. El hecho de identificar que más de una regla podría aplicarse a un elemento es el primer paso para solucionar estos problemas.

### [Propiedades y valores](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#propiedades\_y\_valores) <a href="#propiedades_y_valores" id="propiedades_y_valores"></a>

En su nivel más básico, el CSS consta de dos componentes básicos:

* **Propiedades**: Identificadores legibles por los humanos que indican qué características de estilo (por ejemplo, [`font-size`](https://developer.mozilla.org/es/docs/Web/CSS/font-size), [`width`](https://developer.mozilla.org/es/docs/Web/CSS/width), [`background-color`](https://developer.mozilla.org/es/docs/Web/CSS/background-color)) deseas cambiar.
* **Valores**: A cada propiedad especificada se le asigna un valor que indica cómo quieres que cambien esas características de estilo (por ejemplo, lo que quieres que cambie de la fuente, el ancho o el color de fondo).

La siguiente imagen resalta una sola propiedad y valor. El nombre de la propiedad es `color` y el valor `blue`.

![Una declaración resaltada en el CSS](https://mdn.mozillademos.org/files/16498/declaration.png)

Una propiedad emparejada con un valor se denomina _declaración CSS_. Las declaraciones CSS se colocan dentro de los _bloques de declaración CSS_. La siguiente imagen muestra nuestro CSS con el bloque de declaración resaltado.

![Un bloque de declaración resaltado](https://mdn.mozillademos.org/files/16499/declaration-block.png)

Finalmente, los bloques de declaración CSS se combinan con _selectores_ para producir _conjuntos de reglas CSS_ (o _reglas CSS_). Nuestra imagen contiene dos reglas, una para el selector `h1` y otra para el selector `p`. La regla para `h1` está resaltada.

![La regla para h1 resaltada](https://mdn.mozillademos.org/files/16500/rules.png)

Establecer las propiedades de CSS según valores específicos es la función principal del lenguaje CSS. El motor CSS calcula qué declaraciones se aplican a cada elemento de una página para darle la compaginación y los estilos adecuados.

**Advertencia:** Las propiedades y valores de CSS son sensibles a mayúsculas y minúsculas. La propiedad y el valor de cada par están separados por dos puntos (`:`).

**Prueba a buscar diferentes valores de las siguientes propiedades y escribe reglas CSS que se puedan aplicar a diferentes elementos HTML:**

* [**`font-size`**](https://developer.mozilla.org/es/docs/Web/CSS/font-size)
* [**`width`**](https://developer.mozilla.org/es/docs/Web/CSS/width)
* [**`background-color`**](https://developer.mozilla.org/es/docs/Web/CSS/background-color)
* [**`color`**](https://developer.mozilla.org/es/docs/Web/CSS/color)
* [**`border`**](https://developer.mozilla.org/es/docs/Web/CSS/border)

**Advertencia:** Si una propiedad es desconocida o si un valor no es válido para una propiedad determinada, la declaración se considera _inválida_ y el motor CSS del navegador la ignora por completo.

**Advertencia:** En CSS (y otros estándares web) se ha acordado establecer como estándar la ortografía en inglés de los EE. UU. para solucionar las incertidumbres idiomáticas. Por ejemplo, _siempre_ hay que escribir `color`. Si se escribe `colour`, no funcionará.

#### [Las funciones](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#las\_funciones) <a href="#las_funciones" id="las_funciones"></a>

Si bien la mayoría de valores son palabras clave relativamente simples o valores numéricos, es posible que algunos valores tomen la forma de una función. Un ejemplo sería la función `calc()`. Esta función te permite hacer operaciones matemáticas sencillas desde tu CSS, por ejemplo:

```
<div class="outer"> <div class="box">La caja interior es del 90% - 30px.</div></div>
```



```
.outer {
  border: 5px solid black;
}

.box {
  padding: 10px;
  width: calc(90% - 30px);
  background-color: rebeccapurple;
  color: white;
}
```

Copy to Clipboard

Esto se traduce así:

### [Ejemplo](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#ejemplo) <a href="#ejemplo" id="ejemplo"></a>

Una función consta del nombre de la función y, a continuación, unos paréntesis entre los que se colocan los valores permitidos para esa función. En el caso del ejemplo `calc()` anterior, pedimos que el ancho de esta caja sea del 90% del ancho del bloque que la contiene, menos 30 píxeles. Esto no es algo que podamos calcular con anticipación y simplemente introducir el valor en el CSS, ya que no sabemos cuál será el 90%. Como con todos los valores, la página correspondiente del proyecto MDN tendrá ejemplos de uso para que puedas ver cómo funciona.

Otro ejemplo serían los diversos valores para [`transform`](https://developer.mozilla.org/es/docs/Web/CSS/transform), como `rotate()`.

```
<div class="box"></div>
```



```
.box {
  margin: 30px;
  width: 100px;
  height: 100px;
  background-color: rebeccapurple;
  transform: rotate(0.8turn)
}
```



El resultado del código anterior se ve así:

**Prueba a buscar diferentes valores de las siguientes propiedades y escribe reglas CSS que se apliquen a diferentes elementos HTML:**

* [**`transform`**](https://developer.mozilla.org/es/docs/Web/CSS/transform)
* [**`background-image`**](https://developer.mozilla.org/es/docs/Web/CSS/background-image)**, en particular a valores de gradiente**
* [**`color`**](https://developer.mozilla.org/es/docs/Web/CSS/color)**, en particular a valores rgb/rgba/hsl/hsla**

### [@rules](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#rules) <a href="#rules" id="rules"></a>

Las [`@rules`](https://developer.mozilla.org/es/docs/Web/CSS/At-rule) (leído "at-rules" en inglés) dan al CSS algunas instrucciones sobre cómo comportarse. Algunas `@rules` son simples, con el nombre de la regla y un valor. Por ejemplo, para importar una hoja de estilo adicional a tu hoja de estilo CSS principal, puedes usar `@import`:

```
@import 'styles2.css';
```



Una de las `@rules` más comunes con las que te encontrarás es `@media`, que permite usar [consultas a medios](https://developer.mozilla.org/es/docs/Web/CSS/Media\_Queries) para aplicar CSS solo cuando se dan ciertas condiciones (por ejemplo, cuando la resolución de la pantalla supera un valor determinado o la anchura supera un valor concreto).

En el CSS que se muestra a continuación, tenemos una hoja de estilo que le da al elemento `<body>` un color de fondo rosado. Sin embargo, luego usamos `@media` para crear una sección de nuestra hoja de estilo que solo se aplicará en los navegadores con una ventana gráfica de más de 30em de ancho. Si el navegador es más ancho que 30em, el color de fondo será azul.

```
body {
  background-color: pink;
}

@media (min-width: 30em) {
  body {
    background-color: blue;
  }
}
```



Encontrarás otras `@rules` a lo largo de estas lecciones.

**Prueba a añadir una consulta a medios en tu CSS que cambie los estilos según el ancho de la ventana gráfica. Cambia el ancho de la ventana de tu navegador para ver el resultado.**

### [Abreviaturas](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#abreviaturas) <a href="#abreviaturas" id="abreviaturas"></a>

Algunas propiedades como [`font`](https://developer.mozilla.org/es/docs/Web/CSS/font), [`background`](https://developer.mozilla.org/es/docs/Web/CSS/background), [`padding`](https://developer.mozilla.org/es/docs/Web/CSS/padding), [`border`](https://developer.mozilla.org/es/docs/Web/CSS/border) y [`margin`](https://developer.mozilla.org/es/docs/Web/CSS/margin) se llaman **propiedades abreviadas**. Esto se debe a que permiten establecer varios valores de propiedad en una sola línea, lo que ahorra tiempo y ordena el código.

Por ejemplo, esta línea:

```
/* En propiedades abreviadas con 4 valores, como margin y padding (relleno), los valores se aplican
   según el orden: arriba, derecha, abajo e izquierda (en sentido horario desde la parte superior). También hay otros
   tipos de abreviaturas, como las propiedades abreviadas con 2 valores que establecen el relleno/margen,
   arriba/abajo, y luego izquierda/derecha */
padding: 10px 15px 15px 5px;
```



Hace lo mismo que todas estas juntas:

```
padding-top: 10px;
padding-right: 15px;
padding-bottom: 15px;
padding-left: 5px;
```



Mientras que esta línea:

```
background: red url(bg-graphic.png) 10px 10px repeat-x fixed;
```



Hace lo mismo que todas estas juntas:

```
background-color: red;
background-image: url(bg-graphic.png);
background-position: 10px 10px;
background-repeat: repeat-x;
background-scroll: fixed;
```

Copy to Clipboard

Ahora mismo no pretendemos enseñarlos exhaustivamente: encontrarás muchos ejemplos más adelante en el curso. Te aconsejamos que busques los nombres de las propiedades abreviadas en nuestra [referencia CSS](https://developer.mozilla.org/es/docs/Web/CSS/Reference) para obtener más información.

**Prueba a añadir las declaraciones anteriores a tu CSS para ver cómo afecta al estilo de tu HTML. Experimenta con diferentes valores.**

**Advertencia:** Si bien las propiedades abreviadas a menudo permiten ahorrarte valores, luego restablecerán a sus valores iniciales cualquier valor que no incluyas. Esto asegura que se use un conjunto de valores razonable. Sin embargo, puede resultar confuso si esperas que la propiedad abreviada solo cambie los valores que has introducido.

### [Comentarios](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#comentarios) <a href="#comentarios" id="comentarios"></a>

Al igual que con el HTML, te recomendamos que hagas comentarios en tu CSS para que te ayuden a comprender cómo funciona su código cuando vuelvas a utilizarlo al cabo de varios meses, así como para ayudar a otros que vayan a trabajar con él a entenderlo.

Los comentarios en el CSS comienzan con `/*` y terminan con `*/`. En el bloque de código que encontrarás a continuación, hemos usado comentarios para marcar el inicio de las diferentes secciones de código. Esto es útil para ayudarnos a movernos por la base de código a medida que aumenta: puedes buscar los comentarios en tu editor de código.

```
/* con elementos básicos de aplicación de estilo */
/* -------------------------------------------------------------------------------------------- */
body {
  font: 1em/150% Helvética, Arial, sans-serif;
  padding: 1em;
  margin: 0 auto;
  max-width: 33em;
}

@media (min-width: 70em) {
  /* Prestemos especial atención al tamaño de fuente global. En una pantalla o una ventana grande,
     aumentamos el tamaño de la fuente para conseguir una mejor legibilidad */
  body {
    font-size: 130%;
  }
}

h1 {font-size: 1.5em;}

/* Familiarización con algunos elementos anidados específicos en el DOM */
/* -------------------------------------------------------------------------------------------- */
div p, #id:first-line {
  background-color: red;
  border-radius: 3px;
}

div p {
  margin: 0;
  padding: 1em;
}

div p + p {
  padding-top: 0;
}
```

Copy to Clipboard

Los comentarios también son útiles para _comentar_ temporalmente ciertas partes del código con fines de prueba, por ejemplo, si tratas de encontrar qué parte de tu código causa un error. En el siguiente ejemplo, hemos comentado las reglas para el selector `.special`.

```
/*.special {
  color: red;
}*/

p {
  color: blue;
}
```

Copy to Clipboard

**Añade algunos comentarios al CSS para acostumbrarte a usarlos.**

### [Espacio en blanco](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#espacio\_en\_blanco) <a href="#espacio_en_blanco" id="espacio_en_blanco"></a>

Por espacio en blanco nos referimos los espacios en sí, tabuladores y retornos de carro o intros. De la misma manera que el HTML, el navegador ignora el espacio en blanco dentro del CSS. El valor del espacio en blanco es que puede mejorar la legibilidad.

En el siguiente ejemplo, cada declaración (y el principio/fin de regla) está en una línea propia; esta es posiblemente una buena forma de escribir el CSS, ya que facilita el mantenimiento y la comprensión:

```
body {
  font: 1em/150% Helvética, Arial, sans-serif;
  padding: 1em;
  margin: 0 auto;
  max-width: 33em;
}

@media (min-width: 70em) {
  body {
    font-size: 130%;
  }
}

h1 {
  font-size: 1.5em;
}

div p,
#id:first-line {
  background-color: red;
  border-radius: 3px;
}

div p {
  margin: 0;
  padding: 1em;
}

div p + p {
  padding-top: 0;
}
```

Copy to Clipboard

Podrías escribir exactamente el mismo CSS eliminando la mayoría de los espacios en blanco; este bloque de código es funcionalmente idéntico al primer ejemplo, pero seguro que estarás de acuerdo en que resulta algo más difícil de leer:

```
body {font: 1em/150% Helvetica, Arial, sans-serif; padding: 1em; margin: 0 auto; max-width: 33em;}
@media (min-width: 70em) { body {font-size: 130%;} }

h1 {font-size: 1.5em;}

div p, #id:first-line {background-color: red; border-radius: 3px;}
div p {margin: 0; padding: 1em;}
div p + p {padding-top: 0;}
```

Copy to Clipboard

La manera que elijas para disponer el código suele ser una preferencia personal, aunque cuando comiences a trabajar en equipo es posible que encuentres que el equipo ya tiene su propia guía de estilo que especifica una convención acordada a seguir.

**Advertencia:** Aunque los valores de las declaraciones CSS se separan por espacios, **los nombres de propiedad nunca tienen espacios**.

Por ejemplo, las siguientes declaraciones de CSS son válidas:

```
margin: 0 auto;
padding-left: 10px;
```

Copy to Clipboard

Pero las siguientes no lo son:

```
margin: 0auto;
padding- left: 10px;
```

Copy to Clipboard

¿Ves los errores de espaciado? `0auto` no se reconoce como un valor válido para la propiedad de `margin` (`0` y `auto` son dos valores separados) y el navegador no reconoce `padding-` como una propiedad válida. El valor correcto de propiedad (`padding-left`) se ha separado por un espacio perdido.

Debes asegurarte siempre de separar los valores distintos entre sí por al menos un espacio, pero mantén los nombres de las propiedades y los valores de las propiedades juntos.

**Prueba a jugar con los espacios en blanco de tu CSS y observa qué es lo que se rompe y lo que no.**

### [¿Qué sigue?](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_is\_structured#%C2%BFqu%C3%A9\_sigue) <a href="#que_sigue" id="que_sigue"></a>

Resulta útil entender un poco cómo el navegador toma tu HTML y tu CSS y los convierte en una página web, razón por la cual en el próximo artículo ([Cómo funciona el CSS](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works)) veremos ese proceso.



Hemos aprendido los conceptos básicos de CSS, para qué sirve y cómo escribir hojas de estilo simples. En esta lección vamos a echar un vistazo a cómo un navegador crea una página web a partir de CSS y HTML.

### [¿Cómo funciona realmente el CSS?](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works#%C2%BFc%C3%B3mo\_funciona\_realmente\_el\_css) <a href="#como_funciona_realmente_el_css" id="como_funciona_realmente_el_css"></a>

Cuando un navegador muestra un documento, ha de combinar el contenido con la información de estilo del documento. Procesa el documento en una serie de etapas, que enumeraremos a continuación. Ten en cuenta que este es un modelo muy simplificado de lo que sucede cuando un navegador carga una página web y que cada navegador gestiona el proceso de manera diferente. Pero esto es más o menos lo que sucede.

1. El navegador carga el HTML (por ejemplo, lo recibe de la red).
2. Convierte el [HTML](https://developer.mozilla.org/es/docs/Glossary/HTML) en un [DOM](https://developer.mozilla.org/es/docs/Glossary/DOM) (_Modelo de objetos del documento_). El DOM representa el documento en la memoria del ordenador. Lo explicaremos más detalladamente en la sección siguiente.
3. Entonces, el navegador va a buscar la mayor parte de los recursos vinculados al documento HTML, como las imágenes y los videos incrustados... ¡y también el CSS vinculado! JavaScript aparece un poco más adelante en el proceso, pero no vamos a hablar de ello aún para evitar complicar las cosas.
4. El navegador analiza el CSS y ordena en diferentes «cubos» las diferentes reglas según el tipo de selector. Por ejemplo, elemento, clase, ID, y así sucesivamente. Para cada tipo de selector que encuentre, calcula qué reglas deben aplicarse y a qué nodos en el DOM se les aplica el estilo según corresponda (este paso intermedio se llama árbol de renderización).
5. El árbol de renderización presenta la estructura en que los nodos deben aparecer después de aplicarle las reglas.
6. En la pantalla se muestra el aspecto visual de la página (esta etapa se llama pintura).

El siguiente diagrama ofrece una visión sencilla de este proceso.

![](https://mdn.mozillademos.org/files/11781/rendering.svg)

### [Acerca del DOM](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works#acerca\_del\_dom) <a href="#acerca_del_dom" id="acerca_del_dom"></a>

Un DOM tiene una estructura en forma de árbol. Cada elemento, atributo o bloque en el lenguaje de marcado se convierte en un [nodo DOM](https://developer.mozilla.org/es/docs/Glossary/Node/DOM) con estructura de árbol. Los nodos se definen por su relación con otros nodos DOM. Algunos elementos son padres de nodos secundarios, y estos nodos hijos tienen hermanos.

Comprender el DOM te ayuda a diseñar, depurar y mantener tu CSS porque en el DOM es donde tu CSS se encuentra con el contenido del documento. Cuando comiences a trabajar con las herramientas DevTools (o herramientas del desarrollador) del navegador, te moverás por el DOM mientras seleccionas elementos con el fin de ver qué reglas se aplican.

### [Una representación real de un DOM](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works#una\_representaci%C3%B3n\_real\_de\_un\_dom) <a href="#una_representacion_real_de_un_dom" id="una_representacion_real_de_un_dom"></a>

En lugar de una explicación larga y aburrida, veamos un ejemplo para entender cómo un código HTML se convierte en DOM.

Tomemos el siguiente código HTML:

```
<p>
  Usaremos:
  <span>Hojas</span>
  <span>de estilo</span>
  <span>en cascada</span>
</p>
```



En el DOM, el nodo que se corresponde con nuestro elemento `<p>` es un padre. Sus hijos son un nodo de texto y los tres nodos correspondientes a nuestros elementos `<span>`. Los nodos `SPAN` son también los padres, y los nodos de texto sus hijos:

```
P
├─ "Usaremos:"
├─ SPAN
|  └─ "Hojas"
├─ SPAN
|  └─ "de estilo"
└─ SPAN
    └─ "en cascada"
```

Así es como un navegador interpreta el código HTML anterior, interpreta el árbol DOM y luego lo muestra en el navegador, así:

### [La aplicación de CSS al DOM](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works#la\_aplicaci%C3%B3n\_de\_css\_al\_dom) <a href="#la_aplicacion_de_css_al_dom" id="la_aplicacion_de_css_al_dom"></a>

Pongamos que hemos añadido un poco de CSS a nuestro documento, para darle estilo. Una vez más, el HTML es el siguiente:

```
<p>
  Usaremos:
  <span>Hojas</span>
  <span>de estilo</span>
  <span>en cascada</span>
</p>
```



Supongamos que le aplicamos el CSS siguiente:

```
span {
  border: 1px solid black;
  background-color: lime;
}
```



El navegador analizará el código HTML y creará un DOM a partir de este. A continuación, analizará el CSS. Dado que la única regla disponible en el CSS tiene un selector `span`, el navegador ¡ordenará el CSS muy rápidamente! Aplicará la regla a cada uno de los tres `<span>`, que mostrarán en pantalla la representación visual final.

La salida actualizada es la siguiente:

En nuestro artículo [Depurar el CSS](https://developer.mozilla.org/es/docs/Learn/CSS/Building\_blocks/Debugging\_CSS) que encontrarás en el siguiente módulo, vamos a utilizar las herramientas DevTools del navegador para depurar posibles problemas en el CSS. También aprenderemos más sobre cómo el navegador interpreta el CSS.

### [¿Qué ocurre si un navegador encuentra CSS que no entiende?](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works#%C2%BFqu%C3%A9\_ocurre\_si\_un\_navegador\_encuentra\_css\_que\_no\_entiende) <a href="#que_ocurre_si_un_navegador_encuentra_css_que_no_entiende" id="que_ocurre_si_un_navegador_encuentra_css_que_no_entiende"></a>

En una [lección anterior](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/What\_is\_CSS#soporte\_del\_navegador) mencionamos que no todos los navegadores implementan las novedades de CSS en el mismo momento. Además, no todo el mundo utiliza la última versión de un navegador. Dado que el CSS está en desarrollo constante y, por lo tanto, por delante de lo que los navegadores pueden reconocer, puede que te preguntes qué sucede si un navegador encuentra un selector o una declaración CSS que no reconoce.

La respuesta es que no hace nada y simplemente pasa a la siguiente parte del CSS.

Si un navegador analiza tus reglas y encuentra una propiedad o un valor que no entiende, lo ignora y avanza hasta la declaración siguiente. Esto sucederá si has cometido un error y has escrito mal una propiedad o un valor, o si la propiedad o el valor son demasiado nuevos y el navegador aún no los admite.

Del mismo modo, si un navegador encuentra un selector que no entiende, lo ignorará y pasará al siguiente.

En el siguiente ejemplo hemos utilizado la ortografía británica para la propiedad color, que invalida la propiedad porque no la reconoce. Así que el párrafo no se muestra en azul. Sin embargo, se han aplicado todos los demás estilos del CSS; solo se ha ignorado la línea que no es válida.

```
<p>Quiero este texto en grande, en negrita y en color azul.</p>
```



```
p {
  font-weight: bold;
  colour: blue; /* Ortografía incorrecta de la propiedad color */
  font-size: 200%;
}
```



Este comportamiento es muy útil. Significa que puedes utilizar el CSS nuevo como una mejora, a sabiendas de que no se producirá ningún error si no se entiende: o bien el navegador entiende la característica nueva o no lo hace. Combinado con el funcionamiento del modo en cascada con el hecho de que los navegadores utilizarán la última CSS que encuentren en la hoja de estilo, cuando haya dos reglas con el mismo nivel de especificidad, también puedes ofrecer alternativas para los navegadores que no admiten el CSS nuevo.

Esto funciona especialmente bien cuando quieres utilizar un valor que es bastante nuevo que no admiten todos los navegadores. Por ejemplo, algunos navegadores antiguos no entienden `calc()` como valor. Podríamos dar un valor de sustitución para el ancho de una caja en píxeles, y a continuación dar un ancho con un valor `calc()` de `100% - 50px`. Los navegadores antiguos usarán la versión en píxeles y harán caso omiso de la indicación `calc()`, porque no la entienden. Los navegadores nuevos interpretarán la línea del ancho en píxeles, pero la anularán al llegar a la línea de `calc()` porque aparece después en la cascada.

```
.box {
  width: 500px;
  width: calc(100% - 50px);
}
```



En lecciones posteriores veremos muchas más formas de cómo admitir navegadores diferentes.

### [Y finalmente](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/How\_CSS\_works#y\_finalmente) <a href="#y_finalmente" id="y_finalmente"></a>

Casi has terminado este módulo; solo nos queda una cosa más por hacer. En el próximo artículo, [pondrás en práctica tu conocimiento nuevo](https://developer.mozilla.org/es/docs/Learn/CSS/First\_steps/Styling\_a\_biography\_page) para cambiar el estilo de un ejemplo y probarte con un poco de CSS en el proceso.
