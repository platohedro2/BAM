# Optimism

En esta sección vamos a explicarles los pasos que deben seguir para desplegar un contranto inteligente en la red de <a href="https://www.optimism.io/">Optimist</a>. En este caso, crearemos un contrato inteligente siguiendo el standard ERC-721 usando el <a href="https://docs.openzeppelin.com/contracts/4.x/wizard">Contract wizard</a> de <a href="https://www.openzeppelin.com/">OpenZeppelin</a>, lo subiremos a la red de Optimist a través de la herramienta <a href="https://remix.ethereum.org/">Remix</a> y finalmente, verificaremos nuestra transacción a través de un explorador de bloques.

# ¿Qué es Optimist?

Optimist es un Rollups, primero entendamos eso. Los rollups son <a href="https://www.juniper.net/documentation/mx/es/software/junos/multicast-l2/topics/topic-map/layer-2-understanding.html#:~:text=La%20capa%202%20es%20la,misma%20red%20de%20%C3%A1rea%20local.">protocolos de capa 2</a> que amplían la capacidad de procesamiento de la capa 1 de Ethereum, para ello permite que se procesen las transacciones fuera de la cadena de bloques. Esto hace que la velocidad de procesamiento se incremente. Estos rollups además de mejorar la escalabilidad entre 10 y 100 veces también reducen el costo de gas requerido por transacción.

Optimism está en continua sincronización con Ethereum, las comunicaciones entre ambas cadenas de bloques es constante y se realiza mediante contratos inteligentes,  pudiéndose enviar diferentes criptoactivos entre ellas, como ether o diferentes tokens ERC-20, ERC-721 y ERC-1155.

# Contratos inteligentes en Optimist

Ya que hemos entendido el punto anterior de lo que es Optimist, podemos entender que su constante sincronización permite que tokens de diferentes standares sean admitidos en su red, debido a la compatibilidad existente con Ethereum. Teniendo esto claro, podemos pasar a crear nuestro contrato inteligente con el lenguaje de programación Solidity. ¡A codear!

# Pasos para la construcción de un contrato inteligente

1. Lo primero que vamos a hacer es ir al contract wizard de OpenZeppelin y crear un ERC-721 básico: 

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/Screenshot%20from%202023-05-30%2014-19-04.png?raw=true)
En la sección de "name" otorgale el nombre que desees y puedes seleccionar los 3 campos que ves en la captura.

2. Luego, pasamos a abrir Remix y, crear un nuevo archivo y pegar el código generado por el contract wizard ahí:

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/remix_newFile.png?raw=true)
![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/remix_codePasted.png?raw=true)
Remix automáticamente te creará un conjunto de carpetas y supcarpetas de las cuales no tendrás por qué preocuparte, eso es algo que remix ejecuta para su correcto funcionamiento.

3. Ahora podemos compilar nuestro contrato. Esto para verificar que todo esté funcionamiento de forma correcta y que no haya errores de sintaxis:

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/remix_compiled.png?raw=true)
Si todo está bien, te mostrará un ✅ de color verde que indicará que podemos proceder.
