# ABI

### ¿Qué es ABI?

**ABI** (Application Binary Interface) en el contexto de la informática, es una interfaz entre dos módulos de programa, a menudo entre sistemas operativos y programas de usuario. Dicho en otras palabras, podemos entender al **ABI** como la información que proporciona un [Contrato inteligente](https://www.santander.com/es/stories/smart-contracts) al ser compilado, esta información estará estructurada similar a un [formato JSON](https://www.ibm.com/docs/es/baw/20.x?topic=formats-javascript-object-notation-json-format).

\
EVM (Ethereum Virtual Machine) es el componente central de la red Ethereum, y los contratos inteligentes son fragmentos de código almacenados en la cadena de bloques de Ethereum que se ejecutan en la EVM.&#x20;

Contratos inteligentes escritos en lenguajes de alto nivel como [Solidity](https://docs.soliditylang.org/en/v0.8.2/) o [Vyper](https://vyper.readthedocs.io/en/stable/) deben compilarse en código de bytes ejecutables EVM; cuando se implementa un contrato inteligente, este código de bytes se almacena en la cadena de bloques y se asocia con una dirección. Para Ethereum y la EVM, un contrato inteligente es solo esta secuencia de código de bytes.&#x20;

Para acceder a funciones definidas en lenguajes de alto nivel, los usuarios deben traducir nombres y argumentos en representaciones de bytes para que el código de bytes funcione con ellos.&#x20; para interpretar los bytes enviados en respuesta, los usuarios deben volver a convertir a la tupla de valores de retorno definidos en lenguajes de nivel superior.&#x20;

Los lenguajes que compilan para EVM mantienen convenciones estrictas sobre estas conversiones, pero para realizarlas, se deben conocer los nombres y tipos precisos asociados con las operaciones. El **ABI** documenta estos nombres y tipos con precisión en un formato fácilmente analizable, es muy similar a la **API** (interfaz de programa de aplicación), una representación legible por humanos de la interfaz de un código.&#x20;

**ABI** define los métodos y las estructuras que se utilizan para interactuar con el contrato binario, al igual que **API**, pero en un nivel inferior. La **ABI** indica la persona que llama a la función para codificar la información necesaria, como firmas de funciones y declaraciones de variables en un formato que la EVM puede entender para llamar a esa función en código de bytes; esto se llama codificación **ABI**.&#x20;

La codificación **ABI** está mayormente automatizada, a cargo de compiladores como [REMIX](https://remix.ethereum.org/) o billeteras que interactúan con la cadena de bloques. El contrato **ABI** se representa en formato JSON. Hay especificaciones claras de cómo codificar y decodificar un contrato **ABI**.&#x20;



### ¿Cómo obtener / generar ABI?

La forma más fácil de obtenerlo es a través de [Ethereum REMIX IDE](https://remix.ethereum.org/), en la parte inferior de la sección de *compilar*, lo copias usando el botón **ABI**. Cabe destacar que no es necesario que despliegues el contrato para poder obtener el **ABI**, sencillamente puedes presionar el botón *compilar* o presionas la combinación de teclas: **ctrl + s** y con ello te aparecerá el botón. \


<figure><img src="https://lh5.googleusercontent.com/irrw0SgFg9h5wh-2Y8_jOHdTZAKi55ul0CgbS51yrAfvOd7xIcX45CWFoRNcI-I1LA3Hg59kLorwgZXY-QYml1rQsSoUZDvFPSi_0ykA6kuQYf3n9WY3E5bNSAbP21rvt2c6WkNJ" alt=""><figcaption></figcaption></figure>

\
Otra forma es compilar y generar **ABI** usando [solc](https://www.npmjs.com/package/solc), que proporciona enlaces de JavaScript para [Solidity Compiler](https://github.com/ethereum/solidity). Para instalar **solc**, necesitamos tener **npm**, que viene con [node.js.](https://nodejs.org/en/) Compruebe si *node.js* está instalado en su sistema o no:

```
1$ node  - v
```

\
Si no está instalado, puede descargar la versión *LTS de NodeJS* desde el [sitio web oficial](https://nodejs.org/en/). Ahora vamos a instalar **solc**:

```
$ npm  install  solc
```

\
Compilaremos y generaremos **ABI** para el siguiente contrato, *test.sol*, que es un contrato para incrementar el valor de una variable:


```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.0;

contract test {
    
    uint256 private count = 0;

    function increment() public {
        count += 1;
    }
    
    function getCount() public view returns (uint256) {
        return count;
    }

}
```

\
## Explicación del código anterior.
Línea 1: especificando el tipo [de licencia SPDX](https://spdx.org/licenses/), esto es totalmente adicional después de la versión de Solidity *0.6.8* y para versiones futuras; cada vez que el código fuente de un contrato inteligente se pone a disposición del público, estas licencias pueden ayudar a resolver / evitar problemas de derechos de autor. Si no desea especificar ningún tipo de licencia, puede usar un valor especial **SIN LICENCIA** o simplemente omitir todo el comentario (no generará un error, solo una advertencia).\
Línea 2: Declaración de la versión Solidity.\
Línea 4: Comenzando con la estructura de nuestro contrato, en este caso se le asignó el nombre *test*.\
Línea 6: Declarando una variable privada llamada *cuenta* de tipo entero sin signo y asignándole el valor cero.\
Línea 8-10: Declaración de un incremento de función pública, que aumenta el valor de cuenta en uno cuando se llama.\
Línea 12-14: Declaración de una función pública *getCount* que devolverá el valor de *count* en forma de número entero sin signo.\
Ahora, obtengamos el **ABI** para el contrato anterior.


¿Cómo generar **ABI**?

```
$ solcjs  prueba . sol  -- abi
```

\
Se creará un archivo llamado *test\_sol\_test.abi* en el mismo directorio; tendrá el **ABI** en formato JSON algo como esto:


## ¿Cómo se ve el ABI?

```
[
	{
		"inputs": [],
		"name": "getCount",
		"outputs": [
			{
				"internalType": "uint256",
				"name": "",
				"type": "uint256"
			}
		],
		"stateMutability": "view",
		"type": "function"
	},
	{
		"inputs": [],
		"name": "increment",
		"outputs": [],
		"stateMutability": "nonpayable",
		"type": "function"
	}
]
```
