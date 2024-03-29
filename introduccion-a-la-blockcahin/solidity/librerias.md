# Librerias

No es necesario que escribas cada contrato inteligente de tu proyecto desde cero. Hay muchas bibliotecas de contratos inteligentes de código abierto disponibles, que proporcionan bloques de construcción reutilizables para tu proyecto que pueden salvarte de tener que reinventar la rueda.

### REQUISITOS PREVIOS <a href="#prerequisites" id="prerequisites"></a>

Antes de adentrarte en las bibliotecas de contratos inteligentes, te recomendamos que comprendas bien la estructura de estos documentos. Dirígete a [Anatomía del contrato inteligente](https://ethereum.org/es/developers/docs/smart-contracts/anatomy/), si aún no lo has hecho.

### ¿QUÉ HAY EN UNA BIBLIOTECA? <a href="#whats-in-a-library" id="whats-in-a-library"></a>

Normalmente puedes encontrar dos tipos de bloques de construcción en las bibliotecas de contratos inteligentes: comportamientos reutilizables que puedes añadir a tus contratos, e implementaciones de varios estándares.

#### Comportamientos <a href="#behaviors" id="behaviors"></a>

Cuando escribas contratos inteligentes, hay una gran posibilidad de que te encuentres escribiendo patrones similares una y otra vez, como asignar una dirección de _administrador_ para realizar operaciones protegidas en un contrato, o añadir un botón de _paro_ de emergencia en caso de producirse un problema inesperado.

Las bibliotecas de contratos inteligentes suelen proporcionar implementaciones reutilizables de estos comportamientos como [bibliotecas](https://solidity.readthedocs.io/en/v0.7.2/contracts.html#libraries) o a través de [herencia](https://solidity.readthedocs.io/en/v0.7.2/contracts.html#inheritance) en Solidity.

Como ejemplo, a continuación se muestra una versión simplificada del contrato de [`Ownable`](https://github.com/OpenZeppelin/openzeppelin-contracts/blob/v3.2.0/contracts/access/Ownable.sol) de la [biblioteca de contratos OpenZeppelin](https://github.com/OpenZeppelin/openzeppelin-contracts), que diseña una dirección como el propietario de un contrato y proporciona un modificador para restringir el acceso a un método únicamente a dicho propietario.

```
1contract Ownable {2    address public owner;3
4    constructor() internal {5        owner = msg.sender;6    }7
8    modifier onlyOwner() {9        require(owner == msg.sender, "Ownable: caller is not the owner");10        _;11    }12}13
Mostrar todo Copiar
```

Para utilizar un bloque de construcción como este en tu contrato, primero tendrás que importarlo y, a continuación, ampliarlo en tus propios contratos. Esto te permitirá utilizar el modificador proporcionado por el contrato base `"poseíble"` para asegurar sus propias funciones.

```
1import ".../Ownable.sol"; // Path to the imported library2
3contract MyContract is Ownable {4    // La siguiente función solo puede solicitarla el propietario5    function secured() onlyOwner public {6        msg.sender.transfer(1 ether);7    }8}9
 Copiar
```

Otro ejemplo popular es [SafeMath](https://docs.openzeppelin.com/contracts/3.x/utilities#math) o [DsMath](https://dappsys.readthedocs.io/en/latest/ds\_math.html). Se trata de bibliotecas (en oposición a los contratos base) que proveen funciones aritméticas con controles de desbordamiento, que no proporciona el lenguaje. Recomendamos utilizar cualquiera de estas bibliotecas en lugar de operaciones aritméticas nativas para proteger tu contrato contra desbordamientos, que pueden tener consecuencias nefastas.

#### Estándares <a href="#standards" id="standards"></a>

Para facilitar la [composibilidad e interoperabilidad](https://ethereum.org/es/developers/docs/smart-contracts/composability/), la comunidad Ethereum ha definido varios estándares en forma de **ERC**. Puedes leer más sobre ellos en la sección de [estándares](https://ethereum.org/es/developers/docs/standards/).

Al incluir un ERC como parte de sus contratos, recomendamos buscar implementaciones estándar, en lugar de intentar desplegar las tuyas. Muchas bibliotecas de contratos inteligentes incluyen implementaciones para los ERC más populares. Por ejemplo, el ubicuo [ERC20 fungible token estándar](https://ethereum.org/es/developers/tutorials/understand-the-erc-20-token-smart-contract/) puede encontrarse en [HQ20](https://github.com/HQ20/contracts/blob/master/contracts/token/README.md), [DappSys](https://github.com/dapphub/ds-token/) y [OpenZeppelin](https://docs.openzeppelin.com/contracts/3.x/erc20). Adicionalmente, algunos ERC también proveen implementaciones canónicas como parte del propio ERC.

Vale la pena mencionar que algunos ERC no son autónomos, sino adiciones a otros ERC. Por ejemplo, [ERC2612](https://eips.ethereum.org/EIPS/eip-2612) añade una extensión a ERC20 para mejorar su usabilidad.

### CÓMO AGREGAR UNA BIBLIOTECA <a href="#how-to" id="how-to"></a>

Consulta siempre la documentación de la biblioteca que estás incluyendo para obtener instrucciones específicas sobre cómo incluirla en tu proyecto. Varias bibliotecas de contratos de Solidity están empaquetadas usando `npm`, así que puedes simplemente `instalar npm` de ellas. La mayoría de las herramientas para [compilar](https://ethereum.org/es/developers/docs/smart-contracts/compiling/) contratos buscarán en tu `node_modules` las bibliotecas de contratos inteligentes, así que puedes hacer lo siguiente:

```
1// Esto cargará la biblioteca @openzeppelin/contracts desde tu node_modules2import "@openzeppelin/contracts/token/ERC721/ERC721.sol";3
4contract MyNFT is ERC721 {5    constructor() ERC721("MyNFT", "MNFT") public { }6}7
 Copiar
```

Independientemente del método que utilices, al incluir una biblioteca, siempre vigila la versión del [lenguaje](https://ethereum.org/es/developers/docs/smart-contracts/languages/). Por ejemplo, no puede utilizar una biblioteca para Solidity 0.6 si estás escribiendo tus contratos en Solidity 0.5.

### CUÁNDO SE DEBE UTILIZAR <a href="#when-to-use" id="when-to-use"></a>

Usar una biblioteca de contratos inteligentes para tu proyecto tiene varias ventajas. En primer lugar y principalmente, te ahorra tiempo al proporcionarte los bloques de construcción listos para que los puedas incluir en tu sistema, en lugar de tener que codificarlos tú mismo.

La seguridad también es un beneficio importante. Las bibliotecas de contratos inteligentes de código abierto también suelen ser objeto de un severo escrutinio. Dado que muchos proyectos dependen de ellos, existe un fuerte incentivo por parte de la comunidad para mantenerlos bajo una constante revisión. Es mucho más común encontrar errores en el código de aplicación que en las bibliotecas de contratos reutilizables. Algunas bibliotecas también son sometidas a [auditorías externas](https://github.com/OpenZeppelin/openzeppelin-contracts/tree/master/audit) por seguridad adicional.

Sin embargo, el uso de bibliotecas de contratos inteligentes conlleva el riesgo de incluir código con el que no estés familiarizado en tu proyecto. Es tentador importar un contrato e incluirlo directamente en tu proyecto, pero sin entender bien lo que hace ese contrato, puedes estar introduciendo inadvertidamente un problema en tu sistema debido a un comportamiento inesperado. Asegúrate siempre de leer la documentación del código que estás importando y, a continuación, revisa el código antes de incluirlo en tu proyecto.

Por último, al decidir si incluir o no una biblioteca, considera su uso general. Si seleccionas una que se suela adoptar con frecuencia la ventaja será que, como la utiliza una comunidad de personas mayor, hay más ojos controlando los posibles errores. La seguridad debe ser tu enfoque principal durante la redacción de contratos inteligentes.

### HERRAMIENTAS RELACIONADAS <a href="#related-tools" id="related-tools"></a>

**Contratos de OpenZeppelin:** _**La biblioteca más popular para el desarrollo seguro de contratos inteligentes.**_

* [Documentación](https://docs.openzeppelin.com/contracts/)
* [GitHub](https://github.com/OpenZeppelin/openzeppelin-contracts)
* [Foro de la comunidad](https://forum.openzeppelin.com/c/general/16)

**DappSys:** _**Bloques de creación simples, flexibles y seguros para contratos inteligentes.**_

* [Documentación](https://dappsys.readthedocs.io/)
* [GitHub](https://github.com/dapphub/dappsys)

**HQ20:** _**Un proyecto de Solidity con contratos, bibliotecas y ejemplos para ayudarte a construir aplicaciones distribuidas con todas las características para el mundo real.**_

* [GitHub](https://github.com/HQ20/contracts)

\
