# Estándares de contratos

## Tokens

\
El "token": la herramienta más poderosa e incomprendida de blockchain.

Un token es una _representación de algo en la cadena de bloques_ . Este algo puede ser dinero, tiempo, servicios, acciones en una empresa, una mascota virtual, cualquier cosa. Al representar las cosas como tokens, podemos permitir que los contratos inteligentes interactúen con ellos, los intercambien, los creen o los destruyan.

### Pero primero, café , una introducción a los contratos de tokens

Gran parte de la confusión que rodea a los tokens proviene de la combinación de dos conceptos: _los contratos de tokens y los tokens_ reales .

Un _contrato de token_ es simplemente un contrato inteligente de Ethereum. "Enviar tokens" en realidad significa "llamar a un método en un contrato inteligente que alguien escribió e implementó". Al final del día, un contrato de fichas no es mucho más que un mapeo de direcciones a saldos, además de algunos métodos para sumar y restar de esos saldos.

Son estos saldos los que representan los _tokens_ mismos. Alguien "tiene fichas" cuando su saldo en el contrato de fichas no es cero. ¡Eso es todo! Estos saldos podrían considerarse dinero, puntos de experiencia en un juego, escrituras de propiedad o derechos de voto, y cada una de estas fichas se almacenaría en diferentes contratos de fichas.

### Diferentes tipos de fichas

Tenga en cuenta que hay una gran diferencia entre tener dos derechos de voto y dos escrituras de propiedad: cada voto es igual a todos los demás, ¡pero las casas generalmente no lo son! Esto se llama [fungibilidad](https://en.wikipedia.org/wiki/Fungibility) . _Los bienes fungibles_ son equivalentes e intercambiables, como Ether, monedas fiduciarias y derechos de voto. _Los bienes no fungibles_ son únicos y distintos, como las escrituras de propiedad o los objetos de colección.

En pocas palabras, cuando se trata de bienes no fungibles (como su casa) le importa _cuáles_ tiene, mientras que en los bienes fungibles (como su estado de cuenta bancaria) lo que importa es _cuánto_ tiene.

### Estándares

Aunque el concepto de un token es simple, tienen una variedad de complejidades en la implementación. Debido a que todo en Ethereum es solo un contrato inteligente, y no hay reglas sobre lo que deben hacer los contratos inteligentes, la comunidad ha desarrollado una variedad de **estándares** (llamados EIP o ERC) para documentar cómo un contrato puede interoperar con otros contratos.

Probablemente haya oído hablar de los estándares de token ERC20 o ERC721, y es por eso que está aquí. Dirígete a nuestras guías especializadas para conocer más sobre estos:

* [ERC20](https://docs.openzeppelin.com/contracts/3.x/erc20) : el token estándar más extendido para activos fungibles, aunque algo limitado por su simplicidad.
* [ERC721](https://docs.openzeppelin.com/contracts/3.x/erc721) : la solución de facto para tokens no fungibles, a menudo utilizados para coleccionables y juegos.
* [ERC777](https://docs.openzeppelin.com/contracts/3.x/erc777) : un estándar más rico para tokens fungibles, que permite nuevos casos de uso y se basa en aprendizajes anteriores. Compatible con versiones anteriores de ERC20.
* [ERC1155](https://docs.openzeppelin.com/contracts/3.x/erc1155) : un estándar novedoso para múltiples tokens, que permite que un solo contrato represente múltiples tokens fungibles y no fungibles, junto con operaciones por lotes para una mayor eficiencia del gas.
