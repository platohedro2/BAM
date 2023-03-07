# Cómo funciona la EVM

**La** [**Ethereum**](https://academy.bit2me.com/que-es-optimism/) **Virtual Machine, es una de las piezas claves en el funcionamiento de la** [**blockchain**](https://academy.bit2me.com/que-es-un-nodo-ethereum-2-0/) **de Ethereum. Su función es la de permitir la ejecución de programas o** [**smart contracts**](https://academy.bit2me.com/que-son-los-smart-contracts/) **con la finalidad de desplegar sobre dicha blockchain una serie de funcionalidades añadidas para que los usuarios puedan disfrutar de las mismas.**

[**Contenidos Previos Recomendados**](https://academy.bit2me.com/que-es-ethereum-virtual-machine-evm/#723916656c4e51201)

La Ethereum Virtual Machine o EVM, es una máquina virtual que forma parte del ecosistema blockchain de [**Ethereum**](https://academy.bit2me.com/que-es-ethereum-eth-criptomoneda/). Esta es capaz de ejecutar una amplia gama de instrucciones que le permiten una gran flexibilidad a la hora de realizar distintas operaciones.

Sin embargo, para hacer más sencilla la programación para esta máquina virtual se creo un lenguaje especializado de alto nivel llamado [Solidity](https://solidity-es.readthedocs.io/es/latest/). A través de este [lenguaje de programación](https://academy.bit2me.com/top-5-de-lenguajes-de-programacion-de-smart-contracts/) se facilita la creación de los [**smart contracts**](https://academy.bit2me.com/que-son-los-smart-contracts/). En primer lugar se transforma Solidity a los [**códigos de operación (OP\_CODES)**](https://es.wikipedia.org/wiki/C%C3%B3digo\_de\_operaci%C3%B3n) y luego a un bytecode. Este bytecode es finalmente ejecutado por la EVM para realizar las operaciones especificadas en un smart contract. Todo ello hace que la EVM puede funcionar como un computador de verdad, ejecutando desde las más sencillas hasta las más complejas operaciones.

En pocas palabras, dada la característica descentralizada de Ethereum y su capacidad de almacenar smart contracts en los [**nodos**](https://academy.bit2me.com/que-es-un-nodo/) de la red, y que con EVM pueden ejecutarse las órdenes programadas en dichos smart contracts, Ethereum se convierte en un gran ordenador mundial descentralizado. Uno que es capaz de realizar instrucciones que lleven a la resolución de cualquier tarea específica. De hecho, puede resolver casi cualquier problema computacional y todo esto ocurre dentro de la misma red Ethereum.

Todas estas instrucciones se encuentran escritas en los llamados contratos inteligentes de Ethereum.  Estos contratos son un tipo de cuenta que posee su propio código, y se habilita desde el mismo momento en el que llegan a la blockchain. Lo mejor de todo es que para poder usar el potencial de EVM tan solo debemos tener algo de ether e interactuar con alguna [**DApp**](https://academy.bit2me.com/que-son-las-dapps/), contrato inteligente o hacer nuestro propio contrato. No existe ninguna limitación, cualquier puede aprovechar el poder que EVM tiene a su disposición.

Suena increíble y lo es, EVM es un trabajo de desarrollo enorme que requirió de enorme esfuerzos por parte de gente muy talentosa, y que conocerás a continuación.

### ¿Quién creó la EVM?

Las mentes maestras detrás del desarrollo de la EVM son **Gavin Woods** y **Greg Colvin**. Gavin Woods fue quien creó el conocido [**Yellow Paper de Ethereum**](https://ethereum.github.io/yellowpaper/paper.pdf). En dicho documento técnico, se especifican las ideas y capacidades inicial de la EVM. Por otro lado, Greg Colvin es conocido como el principal desarrollador de la EVM.

Estas dos personas y el equipo que las acompañó permitió la creación de la EVM. Una tecnología que transformó a Ethereum en un ecosistema único dentro de las demás tecnologías que usan blockchain. Todo gracias a que EVM es una parte integral del funcionamiento interno de Ethereum y representa una verdadera innovación en el desarrollo de estas tecnologías.

* ![Gavin Woods creador de la EVM](https://academy.bit2me.com/wp-content/uploads/2019/11/gavin-woods.webp)
* ![Greg Colvin programador de la EVM](https://academy.bit2me.com/wp-content/uploads/2019/11/greg-colvin.webp)

1. [1](https://academy.bit2me.com/que-es-ethereum-virtual-machine-evm/)
2. [2](https://academy.bit2me.com/que-es-ethereum-virtual-machine-evm/)

*

### ¿Cómo funciona la Ethereum Virtual Machine (EVM)?

Con la finalidad de evitar que algún programador pueda atentar contra la seguridad de la red, la EVM realiza una completa abstracción del sistema. Manejando el acceso a los recursos de los computadores y limitando sus acciones en un ambiente controlado o de máquina virtual. A su vez, la EVM permite simplificar el desarrollo y actualización de aplicaciones y características disponibles para las aplicaciones descentralizadas.

La EVM permite el diseño y la ejecución de smart contract. Además gracias a Solidity crear estos smart contracts resulta muy sencillo y manejable. Aunque la EVM por sí misma no es capaz de ejecutar directamente este lenguaje, si lo hace por medio de una técnica conocida como compilación de instrucciones.

Por su parte, Solidity es un lenguaje de programación de alto nivel  muy similar al **JavaScript** y al **C++.** Este lenguaje está orientado a la creación de contratos inteligentes. De esta forma, la mayor parte del código fuente de los contratos está escrito en este lenguaje y luego se compilan en códigos de operación comprensible para la EVM.

La EVM utiliza estos códigos de operación (OP\_CODES) para realizar tareas específicas. Estas limitaciones llevan a al EVM a crear métodos de trabajo que le permitan realizar sus operaciones, entre ellas la más importante es la memoria de contratos. Dicha memoria sirve para almacenar información a la que la EVM puede acceder rápidamente. Por otra parte, para almacenar datos de manera indefinida y hacerlos accesibles para futuras ejecuciones de contratos, se puede usar el almacenamiento por contratos. Esta actúa esencialmente como una base de datos pública, desde la cual los valores se pueden leer externamente sin tener que enviar una transacción al contrato, es decir, sin comisiones.

### OP\_CODES y Bytecode, las fundaciones de la Ethereum Virtual Machine

Los OP\_CODES son una parte muy importante y esencial de la EVM. Estos códigos de operación son los que definen las operaciones válidas que la EVM puede realizar. En EVM existe la capacidad de ejecutar hasta 256 OP\_CODES distintos, aunque en la actualidad no existen esta cantidad de códigos definidos. La razón es que el desarrollo de EVM no ha requerido de la creación de tales códigos y los desarrolladores son cuidadosos con incluir nuevos códigos debido a las limitaciones en sus números.

![Un sencillo ejemplo de Solidity uno de los lenguajes usados para programar para la EVM](https://academy.bit2me.com/wp-content/uploads/2019/11/ejemplo-de-solidity.webp)

Un aspecto importante de los OP\_CODES, es que este es un nivel intermedio de programación para la EVM. El primer nivel vendría dado por Solidity y los lenguajes de programación de alto nivel similares a este. Un segundo nivel de profundidad serían los OP\_CODES. Por último, tendríamos el bytecode resultado de compilar los OP\_CODES en el equivalente a lenguaje máquina de la EVM, algo prácticamente imposible de entender y escribir por un ser humano.

Sin embargo, al ser Ethereum una blockchain pública y ser un proyecto que aboga por la apertura y transparencia, el lenguaje bytecode de la EVM se puede descompilar. Es decir, podemos transformar el bytecode a OP\_CODES y de allí llevarlo a un lenguaje cercano a Solidity. Esto es importante puesto que brinda a EVM la capacidad de mantener de forma abierta y clara el contenido de un smart contract. Además de permitir reconocer la ABI de la que dispone. Un dato importante puesto que se trata básicamente de cómo puede codificar llamadas de un contrato para el EVM y, al revés, cómo leer los datos de las transacciones que genera dicho contrato.

![Todos los OP\_CODES de la EVM](https://academy.bit2me.com/wp-content/uploads/2019/11/op-codes-evm.webp)

### Evolución futura de la EVM

La red de Ethereum ha sido nombrada como la computadora global debido a que cada uno de los nodos conectados a la red, ejecuta una instancia de la EVM. Al mismo tiempo que todos realizan las instrucciones de forma idéntica con el fin de lograr y mantener un consenso sobre el estado del sistema. Esta particularidad de Ethereum hace que su cálculo sea más lento y costoso en comparación con un ordenador común. Pero le brinda mayores ventajas, como por ejemplo una alta defensa a las [fallas bizantinas](https://academy.bit2me.com/que-es-falla-bizantina/), una mayor protección e integridad de los datos y una mayor resistencia a la censura.

Así, Ethereum funciona como una computadora mundial descentralizada de uso general en una red entre pares. Los smart contract y las [**DApps**](https://academy.bit2me.com/que-son-las-dapps/) desarrolladas en la EVM podría incluso asumir las funciones de [Internet](https://academy.bit2me.com/que-es-helium-hnt/) tal y como las conocemos. Además, podría permitirnos la creación de economías más estables ya que su funcionamiento puede ser garantizado y no está sujeto a interpretaciones humanas.

Con la aplicación de elementos como la distribución de archivos, la ejecución de contratos inteligentes, las aplicaciones descentralizadas y muchos otros, se elimina la confianza en terceros, ya que si no se cumplen los términos programados, simplemente el contrato no se ejecutará.

Sin embargo, podemos comparar su nacimiento y desarrollo con la Internet de los años 90. Nadie tiene idea lo que traerá en el futuro. Pero sin duda alguna, la EVM evolucionará con el tiempo y le permitirá a la red convertirse en una mucho más sólida. Donde seguramente veremos las acciones de Ethereum subir, así como el valor de su [token](https://academy.bit2me.com/que-es-near-protocol/).

### ¿Cuánto sabes, criptonauta?

¿La EVM puede ampliarse en funcionalidades?

#### ¡CIERTO!

Una de las principales características de la EVM es que esta puede ampliarse en funcionalidades, pero los desarrolladores sin cuidadosos en incluir nuevas debido a la poca capacidad de agregar OP\_CODES al sistema. Pese a ello, la EVM puede mejorarse para ser incluida en toda clase de dispositivos y es un trabajo en progreso dentro de la comunidad Ethereum con el fin de masificar aún más su uso.

### Característica de las EVM

La Ethereum Virtual Machine es un software que posee muchas características o cualidades tanto positivas como negativas. Entre ellas podemos mencionar:

1. La EVM está enfocada en proporcionar seguridad y ejecutar códigos no confiables en computadoras de todo el mundo.
2. Las aplicaciones descentralizadas y los contratos inteligentes desarrollados en la EVM son completamente descentralizados y distribuidos. Por lo que no requiere de la participación de terceros. Ni pueden ser modificadas ni alteradas.
3. La EVM permite el desarrollo de una mayor cantidad de aplicaciones, y que éstas puedan ejecutarse sobre una misma red blockchain, sin afectar otras operaciones.
4. Los contratos inteligentes diseñados en la EVM son invariables y pueden ejecutarse y hacerse cumplir por sí mismo, de una manera autónoma y automática. Con lo que se elimina la burocracia, los altos costos y el tiempo de espera típicos en los contratos tradicionales.
5. La EVM es sustancialmente menos eficiente que muchas otras máquinas virtuales convencionales. Esto se debe a que principalmente su diseño se basó en la utilidad del momento y no en el alto rendimiento.
6. Los cambios y mejoras experimentados por la EVM han sido pocos hasta ahora. Por lo que no está optimizada en cuanto a la velocidad para distintas plataformas de hardware.
7. El diseño de la EVM no está dirigido a la portabilidad, lo que limita lo espacios en los que dicha máquina virtual puede implementarse.



\
