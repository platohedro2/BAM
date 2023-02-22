# Testnets y Faucets

Las redes son diferentes entornos de Ethereum a los que puede acceder para casos de uso de desarrollo, prueba o producción. Dado que Ethereum es un protocolo, puede haber múltiples "redes" independientes que se ajusten al protocolo sin interactuar entre sí.

Su cuenta de Ethereum funcionará en las diferentes redes, pero el saldo de su cuenta y el historial de transacciones no se transferirán desde la red principal de Ethereum. Para fines de prueba, es útil saber qué redes están disponibles y cómo obtener testnet ETH para jugar. En general, por consideraciones de seguridad, no se recomienda reutilizar cuentas de red principal en redes de prueba o viceversa.

### REQUISITOS PREVIOS <a href="#prerequisites" id="prerequisites"></a>

Debe comprender los [conceptos básicos de Ethereum](https://ethereum.org/en/developers/docs/intro-to-ethereum/) antes de leer sobre las diferentes redes, ya que las redes de prueba le darán una versión barata y segura de Ethereum para jugar.

### REDES PÚBLICAS <a href="#public-networks" id="public-networks"></a>

Las redes públicas son accesibles para cualquier persona en el mundo con una conexión a Internet. Cualquiera puede leer o crear transacciones en una cadena de bloques pública y validar las transacciones que se están ejecutando. El consenso entre pares decide sobre la inclusión de transacciones y el estado de la red.

#### Red principal de Ethereum <a href="#ethereum-mainnet" id="ethereum-mainnet"></a>

Mainnet es la principal cadena de bloques pública de producción de Ethereum, donde se producen transacciones de valor real en el libro mayor distribuido.

Cuando las personas y los intercambios discuten los precios de ETH, están hablando de Mainnet ETH.

#### Redes de prueba de Ethereum <a href="#ethereum-testnets" id="ethereum-testnets"></a>

Además de Mainnet, existen redes de prueba públicas. Estas son redes utilizadas por desarrolladores de protocolos o desarrolladores de contratos inteligentes para probar tanto las actualizaciones de protocolo como los posibles contratos inteligentes en un entorno similar al de producción antes de la implementación en Mainnet. Piense en esto como un análogo a los servidores de producción frente a los de ensayo.

Debe probar cualquier código de contrato que escriba en una red de prueba antes de implementarlo en Mainnet. Entre las dapps que se integran con los contratos inteligentes existentes, la mayoría de los proyectos tienen copias implementadas en redes de prueba.

La mayoría de las redes de prueba comenzaron utilizando un mecanismo de consenso de prueba de autoridad autorizado. Esto significa que se elige una pequeña cantidad de nodos para validar transacciones y crear nuevos bloques, poniendo en juego su identidad en el proceso. Alternativamente, algunas redes de prueba cuentan con un mecanismo abierto de consenso de prueba de participación donde todos pueden probar la ejecución de un validador, al igual que Ethereum Mainnet.

ETH en testnets no tiene valor real; por lo tanto, no hay mercados para testnet ETH. Dado que necesita ETH para interactuar realmente con Ethereum, la mayoría de las personas obtienen ETH de testnet de faucets. La mayoría de los grifos son aplicaciones web donde puede ingresar una dirección a la que solicita que se envíe ETH.

**¿Qué red de prueba debo usar?**

Las dos redes de prueba públicas que los desarrolladores de clientes mantienen actualmente son Sepolia y Goerli. Sepolia es una red para desarrolladores de aplicaciones y contratos para probar sus aplicaciones. La red Goerli permite a los desarrolladores de protocolos probar las actualizaciones de la red y permite a los participantes probar validadores en ejecución.

**Sepolia**

**Sepolia es la red de prueba predeterminada recomendada para el desarrollo de aplicaciones** . La red Sepolia utiliza un conjunto de validadores autorizados. Es bastante nuevo, lo que significa que su estado e historia son bastante pequeños. Esto significa que la red se sincroniza rápidamente y que ejecutar un nodo requiere menos almacenamiento. Esto es útil para los usuarios que desean activar rápidamente un nodo e interactuar directamente con la red.

* Conjunto de validadores cerrado, controlado por el cliente y los equipos de prueba
* Nueva red de prueba, menos aplicaciones implementadas que otras redes de prueba
* Rápido para sincronizar y ejecutar un nodo requiere un espacio mínimo en disco

**Recursos**

* [Sitio web](https://sepolia.dev/)
* [GitHub](https://github.com/eth-clients/sepolia)
* [Otterscan](https://sepolia.otterscan.io/)
* [Etherscan](https://sepolia.etherscan.io/)

**grifos**

* [Dientes de agarre](https://grabteeth.xyz/)
* [Grifo PoW](https://sepolia-faucet.pk910.de/)
* [grifo sepolia](https://faucet.sepolia.dev/)
* [Grifo ETH](https://fauceth.komputing.org/)

**Goerli **_**(soporte a largo plazo)**_

_Nota:_ [_la red de prueba de Goerli está obsoleta_](https://ethereum-magicians.org/t/proposal-predictable-ethereum-testnet-lifecycle/11575/17) _y será reemplazada por_ [_Holesovice_](https://github.com/eth-clients/holesovice) _en 2023. Considere migrar sus aplicaciones a Sepolia._

Goerli es testnet para pruebas de validación y replanteo. La red Goerli está abierta para los usuarios que deseen ejecutar un validador de testnet. Por lo tanto, los participantes que deseen probar las actualizaciones del protocolo antes de que se implementen en la red principal deben usar Goerli.

* Conjunto de validador abierto, los participantes pueden probar las actualizaciones de la red
* Estado grande, útil para probar interacciones complejas de contratos inteligentes
* Más tiempo para sincronizar y requiere más almacenamiento para ejecutar un nodo

**Recursos**

* [Sitio web](https://goerli.net/)
* [GitHub](https://github.com/eth-clients/goerli)
* [Etherscan](https://goerli.etherscan.io/)

**grifos**

* [Dientes de agarre](https://grabteeth.xyz/)
* [Grifo PoW](https://goerli-faucet.pk910.de/)
* [grifo goerli](https://faucet.goerli.mudit.blog/)
* [grifo paradigma](https://faucet.paradigm.xyz/)
* [Grifo Alchemy Goerli](https://goerlifaucet.com/)
* [Todo ese nodo Goerli Faucet](https://www.allthatnode.com/faucet/ethereum.dsrv)

Para iniciar un validador en la red de prueba de Goerli, use [la plataforma de lanzamiento del "validador de goerli barato"](https://goerli.launchpad.ethstaker.cc/en/) de ethstaker .

**Rinkeby **_**(soporte a largo plazo)**_

_Nota:_ [_la red de prueba de Rinkeby está obsoleta_](https://blog.ethereum.org/2022/11/30/ropsten-shutdown-announcement) _y ya no recibirá actualizaciones de protocolo. Considere migrar sus aplicaciones a Sepolia._

Una red de prueba de prueba de autoridad para aquellos que ejecutan versiones antiguas del cliente Geth.

**grifos**

* [FaucETH](https://fauceth.komputing.org/) (faucet multicadena sin necesidad de cuenta social)
* [grifo de cadena](https://faucets.chain.link/)
* [grifo paradigma](https://faucet.paradigm.xyz/)
* [grifo Rinkeby](https://faucet.rinkeby.io/)

#### Redes de prueba de capa 2 <a href="#layer-2-testnets" id="layer-2-testnets"></a>

[Capa 2 (L2)](https://ethereum.org/en/layer-2/) es un término colectivo para describir un conjunto específico de soluciones de escalado de Ethereum. Una capa 2 es una cadena de bloques separada que extiende Ethereum y hereda las garantías de seguridad de Ethereum. Las redes de prueba de capa 2 suelen estar estrechamente unidas a las redes de prueba públicas de Ethereum.

**Arbitrum Goerli**

Una red de prueba para [Arbitrum](https://arbitrum.io/) .

**grifos**

* [FaucETH](https://fauceth.komputing.org/) (faucet multicadena sin necesidad de cuenta social)
* [grifo de cadena](https://faucets.chain.link/)
* [grifo paradigma](https://faucet.paradigm.xyz/)

**Goerli optimista**

Una red de prueba para [el optimismo](https://www.optimism.io/) .

**grifos**

* [FaucETH](https://fauceth.komputing.org/) (faucet multicadena sin necesidad de cuenta social)
* [grifo paradigma](https://faucet.paradigm.xyz/)

### REDES PRIVADAS <a href="#private-networks" id="private-networks"></a>

Una red Ethereum es una red privada si sus nodos no están conectados a una red pública (es decir, Mainnet o testnet). En este contexto, privado solo significa reservado o aislado, en lugar de protegido o seguro.

#### Redes de desarrollo <a href="#development-networks" id="development-networks"></a>

Para desarrollar una aplicación Ethereum, querrá ejecutarla en una red privada para ver cómo funciona antes de implementarla. De manera similar a cómo crea un servidor local en su computadora para el desarrollo web, puede crear una instancia local de blockchain para probar su dapp. Esto permite una iteración mucho más rápida que una red de prueba pública.

Hay proyectos y herramientas dedicadas a ayudar con esto. Obtenga más información sobre [las redes de desarrollo](https://ethereum.org/en/developers/docs/development-networks/) .

#### Redes de consorcio <a href="#consortium-networks" id="consortium-networks"></a>

El proceso de consenso está controlado por un conjunto predefinido de nodos que son de confianza. Por ejemplo, una red privada de instituciones académicas conocidas, cada una de las cuales gobierna un solo nodo, y los bloques son validados por un umbral de signatarios dentro de la red.

Si una red pública de Ethereum es como Internet pública, una red de consorcio es como una intranet privada.

\
