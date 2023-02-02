# Intro a Solidity

### Escribir un contrato inteligente

Para comenzar con el desarrollo de contratos inteligentes, debemos estar familiarizados en lo que constituye un lenguaje de programación orientado a objetos (POO). El lenguaje utilizado en este tutorial es **Solidity** (_el lenguaje utilizado para crear contratos inteligentes en Ethereum_) y se implementa en múltiples cadenas como Binance Smart chain, Polygon o Avalanche.

En esta sección, aprenderás el desarrollo de contratos inteligentes con el lenguaje de programación Solidity trabajando en un proyecto que es de muestra. También aprenderás a conectar los diversos componentes de Solidity (variables, tipos y funciones) para crear una DApp completa.

### A partir de dónde estamos construyendo

El requisito previo para este tipo de tutoriales _generalmente_ es que ya tengan una comprensión de los componentes básicos del lenguaje Solidity. Sin embargo, no necesitas preocuparse por eso ahora, porque iremos paso a paso con el código de nuestro poryecto para que lo entiendas fácilmente.

Comenzaremos en nuestro currículum con pequeños fragmentos de código básico e iremos escalando hasta proyectos más avanzados. Para este tutorial, comenzaremos con un proyecto para principiantes. Nuestro primer proyecto es una DApp para almacenar y recuperar datos de la blockchain.

```solidity
// SPDX-License-Identifier: GPL-3.0

pragma solidity >=0.7.0 <0.9.0;

contract Pets {
    string public myPet;

    function setPetName(string memory petName) public {
        myPet = petName;

    }
    function getPetName() public view returns(string memory){
        return myPet;
    }
}

```

La primera línea (_SPDX-License-Identifer_) nos dice que el código fuente tiene licencia GPL-3.0.

La segunda línea "pragma solidity" es donde especificamos la versión de Solidity en la que está escrito nuestro contrato inteligente. Hacemos esto para asegurarnos de usar el compilador correcto.

Un contrato en Solidity es similar a una clase en los lenguajes de programación orientados a objetos. Es una colección de código compuesta por un constructor, variables y funciones. En este ejemplo, 'Pets' es el nombre del contrato. En nuestro contrato tenemos una variable de estado de tipo string que es pública y le dimos el nombre de 'myPet'.

Definimos dos funciones, a veces llamadas 'getters' y 'setters' en programación. La primera función, setPetName, establece el estado o valor de la variable myPet. La segunda función, 'getPetName' recupera el valor guardado en la variable myPet. La gran mayoría de las funciones que escribirás serán setter o getter.

#### Anatomía de una función

```solidity
function functionName(unit x, uint y) public view returns (uint){
    // function body here
}
```

Cada función debe comenzar con la palabra clave `function`, seguida de su nombre `functionName`. Lo que se coloca dentro de los paréntesis (parámetros) son las entradas o los valores que pasará a su función. `Public view return` indica la visibilidad de la función. En este caso, se define que puede ser accesible a los demás contratos, denotados por la palabra clave `public`. La función promete no modificar el estado de la blockchain, denotado por la palabra `view`. Finalmente, `returns` define que la función devolverá un valor y también define el tipo de datos de esa salida.

### Inténtalo tú mismo

Usando [Remix](https://remix.ethereum.org/#optimize=false\&runs=200\&evmVersion=null\&version=soljson-v0.8.7+commit.e28d00a7.js), un IDE en línea, crea un contrato inteligente simple que agregue dos números juntos y luego devuelva el valor.

Debe definir dos funciones dentro de su contrato inteligente: una para hacer el cálculo basado en dos números ​​que el usuario nos pasará y otra para devolver el valor de ese cálculo. Escribiremos un getter para recuperar el valor actual de la variable y un setter para sumar los dos números y actualizar el valor de la variable.

En Remix, crea un nuevo archivo dentro de la carpeta de contratos, `add.sol`. ![crear un archivo dentro de la carpeta de contratos](https://user-images.githubusercontent.com/15346823/179375354-bac53920-028d-4463-8998-675d8a8f57b5.png)

Comience agregando un identificador de licencia, seguido de la versión pragma:

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;
```

A continuación, defina su contrato y, dentro, defina una variable de tipo uint (entero sin signo) y configúrela en cero.

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract AddNumbers{

uint public sum = 0;
}
```

A continuación, escribe la función para sumar dos números que el usuario nos pase y una función para devolver el valor actual de la variable de suma. Así es como debería verse tu contrato:

```solidity
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract AddNums {
uint public sum = 0;

function addNums(uint x, uint y) public {
    sum = x + y;
}

function getSum() public view returns (uint) {
    return sum;
}

}
```

Ahora desplegaremos, implementaremos y probaremos nuestro contrato. Dirígete al tercer ícono desde arriba y presiona `Compile add.sol` ![Compile contract](https://user-images.githubusercontent.com/15346823/179375260-7b7fc34d-19e5-44f1-b549-c78c828c8085.png)

Muévase al cuarto icono en la parte superior y seleccione Javascript VM del menú desplegable en la selección "environment". Esto te dará ether falso y con esto podrás implementar y probar tu contrato. ![JavascriptVM](https://user-images.githubusercontent.com/15346823/179375210-bc843162-dcf0-4337-a9ed-2ca85a3fde7a.png)

Finalmente, presiona el botón `Deploy` para crear una ejemplo de tu contrato con el que interactuaremos y probaremos que la función de suma funcione debidamente. Después de unos segundos, verás un panel de `Deployed Contracts` en la parte inferior izquierda. ![Contrato de implementación](https://user-images.githubusercontent.com/15346823/179375283-76b327d1-185a-4060-a10b-5cef87545095.png)

Pasa dos números enteros, luego presiona el botón addNums. Verás un registro indicando la nueva transacción que acabas de iniciar. ![enteros](https://user-images.githubusercontent.com/15346823/179375306-905213b2-2b60-4f9d-832d-3cb1a7dd1f43.png)

La función addNums suma los dos números, pero no devuelve el nuevo valor. Para que podamos verificar que la función está correcta, necesitamos llamar a nuestra función getter. Presiona el botón `getSum`. Notarás que aparece un nuevo registro. Expande ese registro usando la flecha hacia abajo y desplázate hasta la parte inferior para encontrar un valor llamado "decoded output."

Podrás ver que obtenemos la respuesta correcta: ¡8! Y así, acabas de escribir tu primer contrato inteligente :-) ![resultado](https://user-images.githubusercontent.com/15346823/179375323-dd99fa72-84a3-460f-bcf3-d7d1a977f94d.png)

***

Escritoras: [Cami](https://twitter.com/camiinthisthang), [Fatma](https://twitter.com/fatima39\_fatima), Editoras: [Busayo](https://twitter.com/AmoweO), [Sarah Schwartz](https://twitter.com/schwartzswartz), [Deborah Emeni](https://twitter.com/\_emeni\_deborah), Traductoras: [Dami](https://twitter.com/dakitidami), [Brenda](https://twitter.com/engineerbrenda), [Caro Meneses](https://twitter.com/carmedinat)
