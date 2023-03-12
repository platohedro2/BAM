# Despliegue en Arbitrum

Arbitrum es una solución [optimista](https://ethereum.org/en/developers/docs/scaling/layer-2-rollups/#optimistic-rollups) de capa 2 de Ethereum. Han surgido varias soluciones de escalado para ofrecer una velocidad mejorada y un costo más bajo en la cadena de bloques de Ethereum, incluidos paquetes acumulativos de capa 2, canales estatales (y de pago), cadenas laterales, Plasma y Validium. La diferencia más importante entre estas soluciones es que los paquetes acumulativos y los canales estatales heredan la seguridad de la cadena de bloques de Ethereum que es de capa 1, lo que permite a los desarrolladores construir esencialmente sobre la capa base de Ethereum.&#x20;

Los resúmenes de capa 2 constan de resúmenes optimistas y resúmenes ZK. Ambas son "verdaderas soluciones de capa 2", lo que significa que pueden ejecutar un gran volumen de transacciones a alta velocidad y bajo costo y luego verificar este paquete de transacciones en la capa 1. Con Optimistic rollups, "creemos con optimismo" que las transacciones realmente ocurrieron en la capa 2. Estos paquetes acumulativos son "optimistas" porque los paquetes se consideran "inocentes hasta que se demuestre su culpabilidad" mediante pruebas de fraude y se supone que son correctos cuando se publican en la capa 1, a menos que se haya presentado un desafío durante los 7 días. período de desafío.&#x20;

### Primeros pasos con Arbitrum <a href="#getting_started_with_arbitrum" id="getting_started_with_arbitrum"></a>

En este tutorial, vamos a construir e implementar un contrato inteligente en Arbitrum Rinkeby Testnet, que es una capa 2 para Rinkeby testnet. Se aplican los mismos pasos para Arbitrum One, una capa 2 para la red principal de Ethereum. Para usar Arbitrum Rinkeby Testnet necesitamos algo de ETH de prueba de Rinkeby. Puede obtener su ENLACE de prueba de Rinkeby a través de [Chainlink Faucets](https://faucets.chain.link/) : simplemente pegue la dirección de su billetera, seleccione Rinkeby Ethereum y reclame su ETH de prueba.

Luego, debemos depositar ETH de prueba de Rinkeby para pagar tarifas en Arbitrum Rinkeby Testnet. Navegue hasta el [puente de Arbitrum](https://bridge.arbitrum.io/) , conecte su billetera, ingrese la cantidad de Rinkeby ETH que necesita y haga clic en "Depositar". Pasarán aproximadamente 10 minutos antes de que vea su saldo acreditado en la capa 2: tiempo para tomar un café.

Una vez que haya recibido su ETH de capa 2, configure su billetera Metamask para la red de prueba Arbitrum Rinkeby. Navegue a [Chainlist](https://chainlist.org/) y encuentre los detalles de Arbitrum Rinkeby Network o navegue al [explorador Etherscan](https://testnet.arbiscan.io/) y busque Add Arbitrum Network en el pie de página del sitio web o seleccione Configuración -> Redes -> Agregar red en Metamask y luego ingrese los detalles manualmente.

Nombre de la red: Arbitrum Rinkeby Testnet

URL de red: https://rinkeby.arbitrum.io/rpc

ID de cadena: 421611

Símbolo de moneda: ETH

URL del explorador de bloques: https://testnet.arbiscan.io/

Finalmente, regrese a [Chainlink Faucets](https://faucets.chain.link/) , seleccione Arbitrum Rinkeby y reclame 10 [tokens LINK de prueba](https://testnet.arbiscan.io/token/0x615fbe6372676474d9e6933d310469c9b68e9726) .

### La importancia de los datos de precios precisos y confiables en los contratos inteligentes <a href="#the_importance_of_accurate_and_reliable_price_data_in_smart_contracts" id="the_importance_of_accurate_and_reliable_price_data_in_smart_contracts"></a>

Para expandir los horizontes de lo que es posible con los contratos inteligentes en la capa 2, los desarrolladores necesitan una conexión segura con los recursos fuera de la cadena. Con datos de precios altamente precisos y confiables de los oráculos de Chainlink, los desarrolladores pueden comenzar a crear y probar una amplia gama de aplicaciones DeFi escalables en Arbitrum que dependen del precio de ETH y otros tokens, como protocolos de préstamos, intercambios descentralizados, mercados de predicción y más. .

Si bien estos casos de uso de DeFi requieren datos externos, las cadenas de bloques y las soluciones de capa 2 no pueden acceder de forma nativa a datos externos. Cuando se proporcionan datos a blockchains para facilitar casos de uso avanzados de DeFi, es imperativo que sean seguros y de alta calidad para evitar ataques de oráculo de precios.&#x20;

Los feeds de precios de Chainlink mitigan el riesgo de estos ataques al proporcionar datos agregados de varios proveedores de datos de alta calidad, alimentados en cadena por oráculos descentralizados a través de Chainlink Network. El mecanismo Oracle descentralizado de Chainlink garantiza que los valores del precio final reflejen una amplia cobertura del mercado, lo que significa que el precio final se determina después de agregar un conjunto diverso de precios en todo el mercado en lugar de solo un pequeño subconjunto, teniendo en cuenta otros aspectos como el volumen y la liquidez. . Con Chainlink Price Feeds, los desarrolladores pueden crear aplicaciones DeFi avanzadas que no comprometen la seguridad.

Ahora que entendemos la necesidad de datos de precios precisos y confiables en los contratos inteligentes de Solidity y el importante papel que juegan los oráculos de precios de Chainlink, veremos un ejemplo del uso de un Feed de precios de Chainlink para obtener el último precio de ETH en un Smart de Solidity contrato en Arbitrum.

### Uso de feeds de precios de Chainlink en Arbitrum <a href="#using_chainlink_price_feeds_on_arbitrum" id="using_chainlink_price_feeds_on_arbitrum"></a>

Comience creando un nuevo proyecto de Solidity en su editor de código favorito. El ejemplo completo usando Hardhat con Typescript está disponible en [Github](https://github.com/andrejrakic/chainlink-arbitrum) . Vamos a utilizar las últimas versiones de Solidity y Chainlink.

```
import "@chainlink/contracts/src/v0.8/interfaces/AggregatorV3Interface.sol";
```

Ahora vamos a escribir una función para recuperar datos de Price Feeds de Chainlink Network. Vaya a la [sección Fuentes de datos](https://docs.chain.link/docs/get-the-latest-price/) de la documentación oficial de Chainlink. Vamos a tomar el ejemplo de la función "obtenerPrecio" y modificarlo ligeramente.&#x20;



```
    function getThePrice(address _priceFeedAddress) public view returns (int) {
        AggregatorV3Interface priceFeed = AggregatorV3Interface(_priceFeedAddress);

        (
            uint80 roundID, 
            int price,
            uint startedAt,
            uint updatedAt,
            uint80 answeredInRound
        ) = priceFeed.latestRoundData();

        return price;
    }
```

Puede ver que estamos pasando "priceFeedAddress" como parámetro para hacer que este contrato inteligente sea más escalable. Puede ver la lista completa de todas las direcciones de Price Feed disponibles en Arbitrum Rinkeby Testnet [aquí](https://docs.chain.link/docs/arbitrum-price-feeds/) .

Por ejemplo, si queremos saber el precio de BTC en USD podemos pasar “0x0c9973e7a27d00e656B9f153348dA46CaD70d03d” a nuestra función como parámetro “\_priceFeedAddress”.

### ¡Casi termino! Conozca el indicador de estado del secuenciador L2 <a href="#almost_done-_meet_the_l2_sequencer_health_flag" id="almost_done-_meet_the_l2_sequencer_health_flag"></a>

Las transacciones en Arbitrum se confirman a alta velocidad. Esto se debe al llamado Secuenciador. El Secuenciador es un componente fuera de la cadena que puede ordenar transacciones de usuarios y dar recibos a los usuarios a alta velocidad. Sin embargo, si el secuenciador no está disponible, los usuarios deben enviar sus transacciones a través de Ethereum para que se procesen en Arbitrum. Esto es perjudicial para la experiencia del usuario, y muchas dApps todavía no tienen los recursos para interactuar con Ethereum y Arbitrum en paralelo.

Si no quiere preocuparse por esto en su aplicación, puede usar un oráculo de Chainlink para asegurarse de que el secuenciador esté disponible para los usuarios. Estos son los pasos para hacerlo:

Primero, debemos agregar la siguiente declaración de importación a nuestro código Solidity

```
import "@chainlink/contracts/src/v0.8/interfaces/FlagsInterface.sol";
```

\
\
De acuerdo con los documentos de Chainlink, The L2 Sequencer Health Flag consta de tres actores:

* Clúster de Chainlink (un grupo de nodos de validación): ejecuta el trabajo de OCR cada latido "T" (la frecuencia mínima a la que se configura la fuente de Chainlink para que se actualice).
* La fuente de OCR real que informa el estado del secuenciador; esto podría usarse para usuarios externos en la capa 1 para verificar el estado del protocolo OR (por ejemplo, Arbitrum).
* Validador: esto lo activa la fuente OCR y ejecuta la acción de subir o bajar la bandera si la respuesta actual es diferente de la anterior.

Ahora, necesitamos ampliar nuestro contrato con las siguientes líneas.

```
// Identificador del indicador fuera de línea del Secuenciador en 
la dirección del contrato de Indicadores constante privado FLAG_ARBITRUM_SEQ_OFFLINE = dirección(bytes20(bytes32(uint256(keccak256("chainlink.flags.arbitrum-seq-offline")) - 1))); 
FlagsInterface enlace de cadena internoFlags;

constructor() { 
    chainlinkFlags = FlagsInterface(0x491B1dDA0A8fa069bbC1125133A975BF4e85a91b); 
}
```

\
“0x491B1dDA0A8fa069bbC1125133A975BF4e85a91b” es la dirección del contrato de banderas de Arbitrum Rinkeby. Para verificar las otras direcciones, diríjase a [Chainlink Docs](https://docs.chain.link/docs/l2-sequencer-flag/) .

Una bandera levantada indica que la fuente no se actualizó en el tiempo "T" y sus datos pueden considerarse obsoletos. En otras palabras, el secuenciador se desconectó y su contrato no debería realizar ninguna operación crítica. Cuando el secuenciador vuelve a funcionar y las fuentes de datos de Chainlink de capa 2 se actualizan, puede continuar usando sus contratos como de costumbre. Agreguemos ese cheque adicional.

```
 function getThePrice(address _priceFeedAddress) public view returns (int) {
        bool isRaised = chainlinkFlags.getFlag(FLAG_ARBITRUM_SEQ_OFFLINE);
        if (isRaised) {
            // If flag is raised we shouldn't perform any critical operations
            revert("Chainlink feeds are not being updated");
        }

        AggregatorV3Interface priceFeed = AggregatorV3Interface(_priceFeedAddress);
        (
            uint80 roundID, 
            int price,
            uint startedAt,
            uint updatedAt,
            uint80 answeredInRound
        ) = priceFeed.latestRoundData();
        return price;
    }
```

### Implementación y prueba del contrato inteligente <a href="#deploying_and_testing_the_smart_contract" id="deploying_and_testing_the_smart_contract"></a>

Ahora estamos listos para implementar y probar nuestro contrato. Compile el contrato en [Remix](https://remix.ethereum.org/) , luego, en la pestaña de implementación, cambie el entorno a "Inyectado Web3". Asegúrese de que la billetera esté conectada a Arbitrum Rinkeby Testnet y que la dirección de la billetera a continuación sea para la billetera MetaMask que contiene el ETH obtenido anteriormente. Luego, presione el botón de despliegue y siga los pasos.

El resultado final es una transacción exitosa y un contrato inteligente implementado en Arbitrum Rinkeby Testnet.&#x20;

Para probarlo, simplemente necesitamos llamar a nuestra función "getThePrice" y pasar una de las direcciones de fuente de precios de Chainlink en Arbitrum Rinkeby Testnet como el parámetro "\_priceFeedAddress". Recuerde, puede ver todas las direcciones de fuente de precios disponibles en [Chainlink Docs](https://docs.chain.link/docs/arbitrum-price-feeds/) .

### Resumen <a href="#summary" id="summary"></a>

El popular feed de precios ETH/USD de Chainlink, así como los feeds de precios para LINK/USD, AAVE/USD y BTC/USD están disponibles en Arbitrum. Estos feeds de precios de Chainlink se basan en una infraestructura Oracle descentralizada que consta de numerosos operadores de nodos revisados ​​por seguridad y fuentes de datos premium, lo que genera feeds de datos altamente precisos, disponibles y resistentes a manipulaciones que son inherentemente resistentes a vulnerabilidades como la manipulación de precios inducida por préstamos flash. ataques&#x20;

Este tutorial técnico ha demostrado lo fácil que es escribir e implementar contratos inteligentes híbridos en Arbitrum. Con este conocimiento, podrá comenzar a crear sus propios contratos inteligentes que aprovechen el bajo costo y la alta velocidad de Arbitrum y la utilidad avanzada desbloqueada por Chainlink Price Feeds.&#x20;

Obtenga más información sobre Chainlink visitando [chain.link](https://chain.link/) o lea la documentación en [docs.chain.link](https://docs.chain.link/) . Para hablar sobre una integración, [comuníquese con un experto](https://chainlinkcommunity.typeform.com/to/OYQO67EF) .
