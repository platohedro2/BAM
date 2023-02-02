# Estructura de contrato

Todo contrato inteligente escrito en Solidity posee algunas **características** propias del lenguaje que debes conocer para comenzar a programar tu primer _smart contract._

### Características y configuraciones de Solidity

Las primeras líneas de un contrato inteligente suelen ser configuraciones y/o comentarios para que el compilador de Solidity funcione correctamente. La estructura básica de un contrato inteligente posee:

```c
// SPDX-License-Identifier: GPL-3.0
pragma solidity >=0.7.0 <0.9.0;

contract MyFirstContract {
    // ...
}
```

* **Licencia:** Define qué permisos tendrá el usuario sobre el contrato, pues al ser código abierto, estará a la vista del público. Existen diversas licencias y dependiendo de la misma puede utilizar el contrato libremente, modificarlo o no, etc.
* **Pragma:** Definen la versión del compilador que se usará. Puede ser una versión fija o un rango específico.
* **Contract**: Esta palabra reservada se usa para indicar el cuerpo del contrato, por lo que todo el contenido debe ir dentro del bloque _“contract”_.

Si bien, la licencia puede ser omitida en algunos casos, el resto de las líneas son obligatorias, pues en los casos de prueba, el despliegue de contratos puede hacerse con menos consideraciones, siempre y cuando se cumplan los requerimientos mínimos.

Los despliegues dentro de la red principal de Ethereum, son irreversibles, por lo que siempre se debe tener cuidado de estos detalles y conocer exactamente el propósito de cada elemento y probar bien tu aplicación antes de pasarla a producción.

La estructura de un contrato inteligente escrito en Solidity será siempre la misma para que el compilador no de problemas y tu contrato sea desplegado correctamente en la EVM y posteriormente ser utilizado.
