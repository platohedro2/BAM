# Ajax

Hay una sintaxis especial que puedes usar en JavaScript y que te facilita el trabajo con promesas. Se llama "async / await" y es sorprendentemente fácil de entender y usar.

En este artículo, hablaré de:

1. ¿Qué son las funciones asíncronas?
2. Cómo funcionan las promesas en JavaScript
3. Conceptos básicos de Async / Await
4. Cómo usar async / await con manejo de errores
5. Cómo una función asíncrona devuelve una promesa
6. Cómo utilizar `promise.all()`

Así que vamos allá

### ¿Qué son las funciones asíncronas? <a href="#qu-son-las-funciones-as-ncronas" id="qu-son-las-funciones-as-ncronas"></a>

El término asíncrono se refiere a una situación en la que dos o más eventos no ocurren al mismo tiempo. O en términos más sencillos, pueden suceder varias cosas relacionadas sin esperar a que se complete la acción anterior.

En JavaScript, **las funciones asíncronas** son muy importantes debido a la naturaleza de **un solo subproceso de JavaScript**. Con la ayuda de funciones asíncronas, el bucle de eventos de JavaScript puede encargarse de otras cosas cuando la función solicita algún otro recurso.

Usarías un código asíncrono, por ejemplo, en las API que obtienen un archivo de la red, cuando accedes a una base de datos y devuelves datos de ella, cuando accedes a una transmisión de video desde una cámara web, o si estás transmitiendo la pantalla a un headset de realidad virtual.

### Cómo funcionan las promesas en JavaScript <a href="#c-mo-funcionan-las-promesas-en-javascript" id="c-mo-funcionan-las-promesas-en-javascript"></a>

El objeto **`Promise` ** en JavaScript representa una operación asíncrona (y su valor resultante) que eventualmente se completará (o fallará).

Una **`Promise` ** puede estar en uno de estos estados:

* _pending (pendiente)_: estado inicial, ni cumplida ni rechazada.
* _fulfilled (cumplida)_: significa que la operación se completó con éxito.
* _rejected (rechazada)_: significa que la operación falló.

<figure><img src="https://www.freecodecamp.org/espanol/news/content/images/2021/08/image.png" alt="image"><figcaption></figcaption></figure>

La función que se pasa a una nueva promesa se llama ejecutora. Sus argumentos (`resolve` y`reject`) se denominan callbacks y los proporciona JavaScript. Cuando el ejecutor obtiene el resultado, ya sea ahora o más tarde, debe llamar a una de estas callbacks.

Aquí va un ejemplo de una promesa:

```js
const miPromesa = new Promise(function(resolve, reject) => {
  setTimeout(() => {
    resolve('foo');
  }, 300);
});
```

Y aquí van ejemplos de una promesa cumplida frente a una promesa rechazada:

```js
// promesa cumplida
let  promesa = new  Promise(function(resolve, reject) {
 setTimeout(()  => resolve(new Error("Hecho!")), 1000);
});

// resolve ejecuta la primera funcion en .then
promesa.then(
  result => alert(result), // Muestra "hecho!" depues de 1 segundo
  error => alert(error) // no se ejecuta
);
```

```js
// promesa rechazada
let promesa =  new  Promise(function(resolve, reject)  { 
 setTimeout(()  => reject(new Error("Whoops!")), 1000);
});

// reject ejecuta la segunda funcion en .then
promesa.then(
  result => alert(result), // No se ejecuta
  error => alert(error) // Muestra "Error: Whoops!" despues de 1 segundo
);
```

### Conceptos básicos de Async / Await en JavaScript <a href="#conceptos-b-sicos-de-async-await-en-javascript" id="conceptos-b-sicos-de-async-await-en-javascript"></a>

Tenemos dos partes cuando usamos `async/await` en nuestro código.

En primer lugar, tenemos la palabra clave `async` , que se pone delante de una declaración de función para convertirla en una función async.

Una función asíncrona es una función que sabe que es posible que se use la palabra clave  `await` dentro de ella para invocar código asíncrono.

_La palabra clave `async` se añade a las funciones para que devuelvan una promesa en lugar de un valor directamente._

```jsx
const cargarDatos = async () => {
  const url = "https://jsonplaceholder.typicode.com/todos/1";
  const res = await fetch(url);
  const datos = await res.json();
  console.log(datos);
};
cargarDatos();
```

```jsx
// output en la consola
{
  completed: false,
  id: 1,
  title: "delectus aut autem",
  userId: 1
}
```

### Cómo **usar Async/Await** con manejo de errores <a href="#c-mo-usar-async-await-con-manejo-de-errores" id="c-mo-usar-async-await-con-manejo-de-errores"></a>

Podemos manejar errores usando un bloque try catch como este:

```jsx
const cargarDatos = async () => {
  try{
	  const url = "https://jsonplaceholder.typicode.com/todos/1";
	  const res = await fetch(url);
	  const datos = await res.json();
	  console.log(datos);
  } catch(err) {
    console.log(err)
  }
};

cargarDatos();
```

El try-catch anterior solamente manejará errores al obtener los datos, como una sintaxis incorrecta, nombres de dominio incorrectos, errores de red, etc.

Cuando quieras manejar un mensaje de error del código de respuesta de la API, puedes usar `res.ok` ( `res` es la variable en la que se almacena la respuesta). Te dará un Boolean con el valor verdadero si el código de respuesta está entre 200 y 209.

```jsx
const cargarDatos = async () => {
  try{
	  const url = "https://jsonplaceholder.typicode.com/todos/qwe1";
	  const res = await fetch(url);
	  if(res.ok){ 
	    const datos = await res.json();
	    console.log(datos);
	  } else {
	    console.log(res.status); // 404
	  }
  } catch(err) {
    console.log(err)
  }
};

cargarDatos();

// OUTPUT
// 404
```

### Cómo una función Async devuelve una promesa <a href="#c-mo-una-funci-n-async-devuelve-una-promesa" id="c-mo-una-funci-n-async-devuelve-una-promesa"></a>

Este es uno de los rasgos de las funciones asíncronas — se garantiza que sus valores de retorno se convertirán en promesas. Para manejar los datos devueltos por una función `async` podemos usar una palabra clave `then` para obtener los datos.

```jsx
const cargarDatos = async () => {
  try{
    const url = "https://jsonplaceholder.typicode.com/todos/1";
    const res = await fetch(url);
    const datos = await res.json();
    return datos
  } catch(err) {
    console.log(err)
  }
};

const datos = cargarDatos().then(datos => console.log(datos));
```

**💡 PRO TIP :**\
Si quieres usar un `async-await` para manejar los datos devueltos puedes utilizar un IIFE, pero solo está disponible en Node 14.8 o superior.

```jsx
// usa una IIFE asincrona 
(async () => {
  const datos = await cargarDatos();
  console.log(datos);
})();
```

`await` solo funciona dentro de funciones asíncronas en JavaScript normal. Pero puede usarlo por sí misma con [módulos JavaScript](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Modules).

### Cómo usar Promise.all () en JavaScript <a href="#c-mo-usar-promise-all-en-javascript" id="c-mo-usar-promise-all-en-javascript"></a>

`Promise.all()` es muy útil cuando queremos llamar a varias APIs.

Utilizando una función con `await` de manera tradicional, tenemos que esperar a que se complete cada solicitud antes de pasar a la siguiente. Esto puede ser un problema cuando cada solicitud tarda en completarse. Esto puede hacer que la respuesta sea muy lenta.

Usando `Promise.all()`, podemos llamar a cada una de estas API en paralelo. (Esto es una explicación muy básica  – Para una explicación más detallada consulta [este ](https://anotherdev.xyz/promise-all-runs-in-parallel/)estupendo artículo) .

_Ten cuidado cuando uses `Promise.all()`, – si una de las solicitudes con await falla, todo el .all() falla._

```js
const cargarDatos = async () => {
  try{
    const url1 = "https://jsonplaceholder.typicode.com/todos/1";
    const url2 = "https://jsonplaceholder.typicode.com/todos/2";
    const url3 = "https://jsonplaceholder.typicode.com/todos/3";
    const resultados = await Promise.all([
      fetch(url1),
      fetch(url2),
      fetch(url3)
    ]);
    const promesasDeDatos = await resultados.map(result => result.json());
    const datosFinales = Promise.all(promesasDeDatos);
    return datosFinales
  } catch(err) {
    console.log(err)
  }
};

const datos = cargarDatos().then(datos => console.log(datos));
```

```jsx
// output en la consola
[{
  completed: false,
  id: 1,
  title: "delectus aut autem",
  userId: 1
}, {
  completed: false,
  id: 2,
  title: "quis ut nam facilis et officia qui",
  userId: 1
}, {
  completed: false,
  id: 3,
  title: "fugiat veniam minus",
  userId: 1
}]
```

### Conclusión <a href="#conclusi-n" id="conclusi-n"></a>

En la mayoría de las situaciones, podemos usar `async/await` con un bloque `try catch` para manejar tanto los resultados como los errores.

Por el momento, `await` no funcionará en el código al nivel superior. Esto quiere decir que si estamos fuera de una función asíncrona (`async` ), no podemos usar  `await` sintácticamente. En este caso, lo habitual es agregar `.then/catch` para manejar el resultado final o el error.

_A nivel superior en el_ código _, `await` _ está _disponible en Node.js `v14.8` o superior y solamente en módulos ES. Puedes ver_ más aquí_:_ [_Top-level await is available in Node.js modules | Stefan Judis Web Development_](https://www.stefanjudis.com/today-i-learned/top-level-await-is-available-in-node-js-modules/#top-level-%60await%60-is-available-%22unflagged%22-in-node.js-since-%60v14.8%60)
