# Funciones y  modificaciones

Al igual que en cualquier lenguaje de programación, las funciones son **piezas de código que se encargan de ejecutar instrucciones de forma independiente**. Dentro de Solidity son importantes, pues son el vehículo para que clientes interactúen directamente con los _smart contracts_.

### Declaración de funciones en Solidity

Las funciones son también denominadas métodos en la programación orientada a objetos o procedimientos, si las mismas no devuelven un valor. Todos son términos que se refieren a lo mismo, **instrucciones para realizar una tarea en particular**.

La sintaxis de una función en Solidity tiene algunas particularidades con respecto a otros lenguajes y hasta permite escribirse de formas diferentes:

```c
function multiplication(int a, int b) returns(int) {
    return a * b;
}
function multiplication(int a, int b) returns(int product) {
    product = a * b;
}
```

En primer lugar, la palabra reservada `returns` (en plural) indica el tipo de dato de retorno y se requiere un `return` (en singular) para devolver el mismo. En el segundo ejemplo, el `returns` indica, además del tipo de dato, la variable que será devuelta, debiendo declararse la misma para que la función la retorno y no es necesario el `return`.

Si algo está mal en la declaración de una función, el compilador de Solidity nos notificará y no podremos compilar ni desplegar nuestro contrato. Solidity, al ser un lenguaje fuertemente tipado, nos anticipa a posibles errores que nuestro código pueda tener.

### Visibilidad de las funciones

Las funciones al igual que las variables, pueden implementar los tipos de visibilidades `public`, `private`, `internal` y `external`. **Por defecto, las funciones son todas públicas**.

Son más importante sobre la visibilidad de las funciones, es el poder utilizarlas o no desde afuera del contrato. Si desplegamos el siguiente contrato en remix:

```c
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract ExampleContract {

    function multiplicationPublic(int a, int b) public returns(int) {
        return a * b;
    }

    function multiplicationPrivate(int a, int b) private returns(int) {
        return a * b;
    }
}
```

Veremos lo siguiente:\
![image.png](https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/image\(701\).png)\
Si bien las dos funciones son iguales, la pública puede ser accedida y el entorno de Remix nos permite utilizarla. La función privada, no es visible desde afuera del contrato.

### Tipos de funciones

Además de la visibilidad de las funciones, una característica que Solidity implementa es la posibilidad de que cada función tenga un tipo diferente a partir de su comportamiento. Podemos diferenciar tres tipos:

* `view`: Funciones que solo leen y devuelven dato, no realizan ningún tipo de lógica.
* `pure`: Funciones que siempre devuelven un valor de forma determinista. Por ejemplo, una función de suma siempre devolverá el mismo resultado ante una misma entreda.
* `payable`: Funciones especiales capaces de enviar o recibir ETH.

Exploremos cada una de estos tipos de funciones un poco más.

#### Funciones del tipo vista

Las funciones _view_ pueden considerarse similares a los _getters_ en la programación orientada a objetos. **Devuelven un valor y nada más**.

```c
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract ExampleContract {

    string saludo = "Bienvenido a Platzi!";

    function saludar(int a, int b) public view returns(string) {
        return saludo;
    }
}
```

La función `saludar()` es marcada como _view_ y solo devuelve el valor de una variable. Es importante también tener en cuenta que las **funciones del tipo view no consumen gas**.

#### Funciones puras

En el mundo de la programación, en general, las funciones puras realizan una tarea y **devuelven siempre el mismo valor para una misma entrada**. Pero no modifican el valor de ninguna variable, o sea, **no cambian el estado del contrato**.

```c
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract ExampleContract {

    function multiplication(int a, int b) public pure returns(int) {
        return a * b;
    }
}
```

La función `multiplication()` es marcada como _pure_ debido a que siempre devolverá el mismo resultado al multiplicar los mismos dos números. Esta función si consume gas debido a que realiza un procesamiento.

#### Funciones pagables

Posiblemente las funciones más importantes de todo contrato inteligente. Las funciones `payable` son las únicas de todo el contrato que tienen permitido enviar o recibir Ether.

```c
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract SendETH {
    
    function sendETH(address payable receiver) public payable {
        receiver.transfer(msg.value);
    }
}
```

La función enviará los ETH que reciba utilizando la función `transfer()` de una dirección también marcada como `payable`.

Si despliegas el contrato en Remix, puedes enviar ETH a una dirección de la siguiente manera:

<figure><img src="https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/image(702).png" alt="image.png"><figcaption></figcaption></figure>

Observa que luego de desplegar el contrato inteligente en Remix, la función del tipo `payable` se marca en color rojo. Lo primero que debes hacer es seleccionar una cuenta de la lista que el entorno provee para hacer pruebas.

Selecciona la unidad que quieres enviar, pudiendo ser Ether, Wei o Gwei. Recuerda que un ETH es equivalente a `1.000.000.000.000.000.000` Wei mientras que también es equivalente a `1.000.000.000` Gwei. Finalmente, agrega el monto en el campo _value_ para poder hacer clic en el botón rojo y enviar el Ether. Recuerda que la función recibe por parámetro la dirección de otra cuenta.

Anímate a enviar ETH a otra cuenta de prueba de la lista que Remix provee y habrás logrado tu primera transacción en un contrato inteligente.

### Conclusión

Estas son las características de las funciones que debes dominar. Desde su sintaxis, visibilidad y los diferentes tipos. Son elementales para poder crear contratos con una correcta funcionalidad que integren aplicaciones sin generarle ningún problema a los usuarios ni a sus propios creadores.
