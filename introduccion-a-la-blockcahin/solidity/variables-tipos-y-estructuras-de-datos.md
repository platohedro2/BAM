# Variables, tipos y estructuras de datos

Existen **características generales** que todos los lenguajes de programación implementan y otras tantas propias de cada lenguaje. Solidity tiene las suyas, sintaxis que verás en muchos otros lenguajes de programación y otra serie de características únicas de Solidity.

### Tipos de variable y operadores en Solidity

Solidity, como todo lenguaje de programación, posee una serie de **operadores y tipos de variables** que puedes utilizar para programar la lógica de tu aplicación.

#### Tipado de variables

**Solidity** es un lenguaje fuertemente tipado, lo que significa que debes especificar el tipo de variable cuando la declaras y este no puede cambiar. Esto ayuda enormemente a reducir los errores en el código fuente.

En Solidity puedes encontrar los tipos de variables:

* **Boolean:** Variables binarias que solo pueden contener dos valores, `true` o `false`.
* **String:** Permite guardar cadenas de texto.
* **Números enteros:** Pueden ser de dos tipos, `uint` (enteros que no permiten números negativos) e `int` (enteros que si pueden ser negativos). Contar con variables sin signo nos permite aprovechar al máximo la capacidad de memoria de una variable para guardar números positivos aún más grandes.
* **Address:** El tipo de dato “dirección” es propio de Solidity y te servirá para almacenar direcciones de una cuenta de una _wallet_ de un usuario, o bien, la de otro _smart contract_ dentro del contrato. Para que una dirección pueda recibir Ether, se debe indicar con la palabra reservada `payable`.

<figure><img src="https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/addr.png" alt="addr.png"><figcaption></figcaption></figure>

#### Variables globales

Muchos lenguajes de programación implementan **variables globales que puede invocar y utilizar en todo momento**. En Solidity, podemos encontrar las siguientes variables globales:

* `block`: Información del bloque actual de la transacción.
* `msg`: Información de la llamada.
* `tx`: Información de la transacción.

Cada una de ellas es un objeto con varias propiedades que nos aportan información sobre el contexto de ejecución de la transacción o el estado del contrato. Estas son algunas de las variables más comunes:

* `block.gaslimit`: Límite de gas en el bloque actual
* `msg.data`: Información de la llamada
* `msg.sender`: Dirección de la llamada
* `msg.value`: Número de `wei` enviado
* `tx.gasprice`: Costo de gas de la transacción

El gas es concepto transcendental que debes conocer. Sus distintos valores y unidades de medida parten de un ETH fragmentado en pequeñas partes.

**Denominaciones de Ether:**

| Nombre de unidad | Valor en Wei | Número de Wei             |
| ---------------- | ------------ | ------------------------- |
| Wei (Wei)        | 1 wei        | 1                         |
| Kwei (Baggage)   | 1e3 wei      | 1.000                     |
| Mwei (Lovelace)  | 1e6 wei      | 1.000.000                 |
| Gwei (Shannon)   | 1e9 wei      | 1.000.000.000             |
| Twei (Szabo)     | 1e12 wei     | 1.000.000.000.000         |
| Pwei (Finney)    | 1e15 wei     | 1.000.000.000.000.000     |
| Ether (Buterin)  | 1e18 wei     | 1.000.000.000.000.000.000 |

Observa la particularidad de que cada unidad de medida tiene un nombre especial. Por ejemplo Szabo es el creador del concepto de contratos inteligentes en los años '90 y es un pequeño homenaje a su persona. ¿Te animas a investigar quién es cada uno de estos autores?

#### Operadores lógicos

Para realizar comparaciones o validaciones de variables, puedes implementar operadores lógicos como:

* `[!]`: Comprueba si el valor es falso, convierte un valor booleano a su valor opuesto.
* `[&&]`: Operador _AND_. Comprueba si dos o más valores son verdaderos.
* `[||]`: Operador _OR_. Compueba si al menos uno de dos o más valores es verdadero.
* `[==]`: Comprueba si dos valores son iguales o equivalentes.
* `[!=]`: Comprueba que dos valores no sean iguales o equivalentes.

#### Visibilidad de las variables

Las variables en Solidity puede tener uno de cuatro tipos de visibilidades. Cada uno **permite un alcance o acceso a la variable de diferente manera** que podemos utilizar dependiendo la necesidad.

* `public`: Las variables del tipo públicas, a lo igual que en POO, pueden ser accedidas tanto por fuera como por dentro del contrato.
* `private`: Las variables del tipo privadas solo podrán ser accedidas desde adentro del propio contrato.
* `internal`: Las variables internas solo pueden ser accedidas por el mismo contrato o un contrato que deriva del mismo, o sea, contratos heredados.
* `external`: Las variables externas solo puede ser accedidas desde llamadas de otros contratos. No puede leerse dentro del mismo contrato.

Por defecto, las variables son del tipo `internal`.

### Constructor de un contrato

A lo igual que en la programación orientada a objetos, **los contratos posee un constructor que es la primera función que se ejecuta por única vez al desplegar el mismo**. En él, puede inicializar variables y también capturar variables que el usuario haya enviado para desplegarlo.

```c
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract Storage {

    uint myNumber;
    address myAddress;

    constructor(uint256 number) {
        myNumber = number;
        myAddress = msg.sender;
    }
}
```

En el ejemplo anterior, el constructor recibe una variable del tipo `uint256` que es guardada dentro de una propiedad del contrato. Además, estamos guardando la dirección de la _wallet_ del usuario que desplegó el contrato en otra propiedad del contrato.

### Entorno de desarrollo de Solidity

Ethereum posee su propio entorno de desarrollo denominado [Remix](https://remix.ethereum.org/). Por supuesto que también puedes utilizar VS Code, pero Remix, además de funcionar en la nube, **implementa características para probar nuestros contratos inteligentes en cuestión de segundos**.

Así luce la interfaz de Remix, el IDE en el navegador para desarrollar _smart contracts_ en Solidity:

<figure><img src="https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/image(693).png" alt="image.png"><figcaption></figcaption></figure>

A la izquierda, se encuentra el principal menú de opciones. De arriba hacia abajo encontramos:

* (1) Este es el explorador de archivos, el primero en visualizarse al entrar en Remix. Aquí se encuentran los contratos.
* (2): Buscador dentro del entorno para acceso rápido a tus contratos.
* (3) Configuraciones del compilador de Solidity.
* (4) _deployer_ o desplegador de tus contratos donde puedes elegir la red donde se va a desplegar. También se pueden visualizar y probar las funciones del contrato e interactuar con el mismo una vez hecho el despliegue.

### Despliegue de tu primer contrato

El entorno puede parecer algo confuso al principio, veamos cómo utilizarlo para desplegar tu primer contrato inteligente.

**Paso 1. Programa el contrato inteligente**\
En el centro se encuentra el área de la escritura del contrato, donde se escribe todo el código. Justo debajo se observa la terminal que Remix incluye para lanzar comandos. Puedes utilizar algunos contratos de prueba que Remix trae por defecto.

<figure><img src="https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/image(700).png" alt="image.png"><figcaption></figcaption></figure>

**Paso 2. Compilación del contrato**\
Cuando hayas finalizado el desarrollo de tu contrato, el entorno suele compilar el mismo automáticamente para verificar que todo está correcto. También puede compilarlo tu mismo haciendo clic en el botón “Compile” en la opción número 3 del menú.

<figure><img src="https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/image(696).png" alt="image.png"><figcaption></figcaption></figure>

**Paso 3. Despliegue del contrato**\
Antes del despliegue, puedes configurar en la opción 4 del menú en el entorno donde se lanzará el contrato, la dirección de prueba que quieres usar para el despliegue con ETH sin valor real. También puedes configurar el límite de gas para la transacción o puedes dejar el valor por defecto.

Por ahora, estos ajustes son suficientes para este contrato de prueba. Has clic en el botón naranja “Deploy” para lanzar tu primer contrato.

<figure><img src="https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/image(697).png" alt="image.png"><figcaption></figcaption></figure>

Si no hubo ningún problema con la compilación, el despliegue debe arrojar en la pantalla (y también verás el registro en la terminal) la “palomita verde” de transacción exitosa.

En la parte izquierda, en el menú de despliegue, puedes observar los botones que se habilitan con el contrato que representan a cada una de las funciones del mismo.

![image.png](https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/image\(698\).png)\
Ya puedes comenzar a interactuar con tu contrato haciendo uso de estos botones.

### Conclusión

Esto es tan solo un vistazo rápido de lo que implica crear un contrato y trabajar con el entorno de Remix que será tu mejor aliado para desarrollar y probar contratos. Aún hay mucho por aprender tanto sobre desarrollo de software con Solidity como en el uso de este entorno de desarrollo.
