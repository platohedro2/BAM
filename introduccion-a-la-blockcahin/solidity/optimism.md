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

4. El siguiente paso será desplegar nuestro contrato. Dirígite a la sección de "compilar" y despliega la lista superior para seleccionar una conexión con Metamask:

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/remix_select.png?raw=true)
![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/remix_metamask.png?raw=true)
Esto lo hacemos para poder desplegar nuestro contrato en la red testnet de Metamask.

## Pequeño break

Antes de conectar con nuestra billetera de Metamask, deberemos configurar la red testnet de Optimist (este es un paso que sí vas a desplegar en la red principal, no será necesario que lo hagas), para eso sigue estos pasos: 

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/metamask_1.png?raw=true)
Primero, dale click donde dice "ethereum mainnet" para desplegar una lista, luego dale click al botón "agregar red".

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/metamask_2.png?raw=true)
Segundo, dale click al botón inferior que dice "agregar una red manualmente" e introduce los siguientes datos:

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/metamask_3.png?raw=true)
Finalmente, guarda la nueva red y cambiate a ella en la sección de "redes".

5. Luego de haber establecido la configuración correspondiente en nuestra billetera de Metamask, podemos pasar a seleccionar "Metamask injección" que se encuentra en la lista desplegada anteriormente, esto nos abrirá una ventana de Metamask pidiéndonos autorización para conectarse a nuestra waller: 

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/metamask_connect.png?raw=true)
Dale conectar y con eso estaremos listos para desplegar.

6. Dale click al botón "desplegar", esto te abrirá una ventana de Metamask para que confirmes la transacción, accede a través del botón azul: 

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/remix_desplegar.png?raw=true)
![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/metamask_confirmated.png?raw=true)

7. ¡Excelente! Con esto habrás desplegado tu primer contrato inteligente en la red de Optimist. Si todo salió bien, debería aparecerde un mensaje en la parte inferior derecha con una información:

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/remix_copied_tx.png?raw=true)
¡Estupendo! Ahora, pasemos a verificar nuestra transacción, para ello, copia la dirección de tu contrato como se muestra en esta captura ☝.

8. Dirígete a esta web: https://goerli-optimism.etherscan.io/ Este es el explorador de bloques de la red testnet de Optimist, en ella vas a pegar la dirección de tu contrato:

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/optimist_explorer.png?raw=true)
Dale click ahí para buscar tu contrato.

9. ¡Vualá! Podrás ver tu contrato inteligente y toda su información correspendiente desplegada en la red testnet de Optimist:

![image](https://github.com/Juminstock/BAM/blob/main/.gitbook/assets/optimist_explorer2.png?raw=true)
Con esto habremos finalizado este tutorial.

Esperamos que te haya servido de mucho.
