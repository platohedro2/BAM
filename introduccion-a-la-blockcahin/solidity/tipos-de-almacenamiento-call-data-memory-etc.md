# Tipos de Almacenamiento: call data, memory, etc

Las **variables** pueden tener una ubicación distinta dentro de su almacenamiento en el contrato dependiendo del uso que se les vaya a dar y cómo se utilicen.

### Tipos de almacenamiento de datos

Para especificar la **localización de los datos en un contrato**, veremos a continuación tres posibilidades y dependiendo la misma, una variable tendrá un comportamiento u otro.

### `Storage`

Indica que una variable será guardada dentro de la Blockchain. Siempre podremos obtener un valor desde el _storage_ dado que todo en Blockchain es inmutable. A este tipo de memoria se le conoce como memoria persistente.

### `Memory`

Las variables del tipo _memory_ solo pueden ser usadas mientras se llama a una función. Después de esto, la misma se borrará. Este tipo de variable puede modificarse mientras está en uso.

### `Calldata`

Similar a _memory_, con la diferencia de que aquí las variables no se pueden modificar mientras estén en uso. Si se sabe de antemano que una variable no necesitará modificarse, es buena práctica usar _calldata_ para reducir el consumo de gas.

Por defecto, las variables de estado del contrato son guardadas en el _storage_, mientras que los parámetros de una función son guardados en _memory_. Los únicos tipos de datos a los que se les puede asignar un almacenamiento distinto son los tipos _string_, _array_, _struct_ y _mapping_.

**El tipo de almacenamiento de una variable cambiará el ciclo de vida de la misma**. Haciendo que esta sea modificable o persistente dentro del contrato. Es muy importante entender la diferencia entre cada tipo para saber cuándo es conveniente utilizar cada uno y mejorar el rendimiento de un contrato.
