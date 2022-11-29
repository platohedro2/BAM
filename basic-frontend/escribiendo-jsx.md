# Escribiendo JSX



```
const element = <h1>Hello, world!</h1>;
```



Esta sintaxis de etiquetas no es ni un string ni HTML.

Se llama JSX, y es una extensión de la sintaxis de JavaScript. Se usa con React para describir cómo debería ser la interfaz de usuario.&#x20;

React une la lógica y la interfaz de usuario. Por ejemplo: Un formulario de registro y la función que valida los datos del formulario.

Para lograr esto se usa JSX que es un lenguaje que permite incluir una sintaxis similar a las etiquetas HTML dentro de javascript.

Ejemplo



```
const name = 'Josh Perez';
const element = <h1>Hello, {name}</h1>;
```



En este ejemplo se declara una variable llamada `name` y luego se usa  dentro del JSX envolviéndola dentro de llaves.

Se puede usar cualquier expresión de javascript dentro de _llaves { }_ en JSX. Por ejemplo, insertar el resultado de llamar la función de JavaScript, `formatName(user)`, dentro de un elemento `<h1>`.



```
function formatName(user) {
  return user.firstName + ' ' + user.lastName;
}

const user = {
  firstName: 'Harper',
  lastName: 'Perez'
};

const element = (
  <h1>
    Hello, {formatName(user)}!  </h1>
);

```

\
\


\




\
