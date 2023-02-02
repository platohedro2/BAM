# Eventos

Con cada transacción que un contrato inteligente procesa correctamente, puede haber **partes involucradas e interesadas en ser notificadas de estos cambios de estado** de un proyecto.

### Envío de notificaciones al exterior de la Blockchain

**Los Eventos en Solidity se utilizan para notificar los cambios realizados en un contrato**. Cuando un usuario envía ETH y se quiere notificar a otro de su recepción, puedes emplear este mecanismo para que una aplicación externa reciba el mensaje e informe a dicho usuario.

Los eventos deben ser recibidos por medio de **aplicaciones Web3 que se encuentren observando el contrato y respondiendo a los eventos**. Librerías de Javascript como [Web3.js](https://www.npmjs.com/package/web3) permiten desarrollar este tipo de aplicaciones front end y notificar al usuario de eventos en un contrato.

> En Platzi encontrarás el [Curso de Dapps: Introducción al Desarrollo de Aplicaciones Descentralizadas](https://platzi.com/cursos/intro-dapps/) y el [Curso de Desarrollo Frontend de Aplicaciones Descentralizadas con Web3.Js](https://platzi.com/cursos/frontend-dapps/) en donde aprenderás a desarrollar toda una aplicación que responda y notifique eventos en un contrato. Pero tranquilo que aún es pronto para llegar a eso.\
> :::

#### Implementando eventos

La declaración de un evento y la emisión de una notificación del mismo se realiza de forma simple:

```c
// SPDX-License-Identifier: MIT
pragma solidity >=0.7.0 <0.9.0;

contract Event {

    event Log(address sender, string message);

    function sendMessage() public {
        emit Log(msg.sender, "Este es el mensaje");
    }
}
```

Utilizando la palabra reservada `event`, declara el evento que puede recibir por parámetro todos los datos que el mismo necesite. Para emitir un evento, utiliza la palabra reservada `emit` seguido de la declaración del evento y el pasaje de datos que necesita.

Si emiten un evento, la consola de Remix te permitirá observa los datos de este.

<figure><img src="https://cdn.document360.io/da52b302-22aa-4a71-9908-ba18e68ffee7/Images/Documentation/image(703).png" alt="image.png"><figcaption></figcaption></figure>

También puedes emplear este mecanismo para generar un registro de actividad en un contrato, además de notificar usuarios.

### Conclusión

Estos conceptos son algo avanzado de Solidity debido a que, sin un front-end, puede no tener tanto sentido su implementación. Es importante para ti en este punto de tu aprendizaje conocer su existencia para usarlos en el futuro.

***
