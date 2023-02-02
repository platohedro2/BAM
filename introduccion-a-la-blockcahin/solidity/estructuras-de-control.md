# Estructuras de control

Los lenguajes de programación Turing Completo poseen una serie de estructuras para **controlar la lógica y el flujo de tu código fuente**.

### Estructuras de control en la programación

Las estructuras de control permiten declarar condiciones, agrupar instrucciones de código para ejecutarlas de forma sistemática y organizada las veces que necesitemos. Existen diferentes estructuras en la programación en general, y las que Solidity utiliza también existen en muchos otros lenguajes.

#### 1. Condicionales if - else

Las condiciones _if - else_ son la estructura más básica y simple dentro de la programación, le indican al código que si cierta expresión se cumple, se debe ejecutar el bloque de código que está relacionado con tal condición. Es una manera de bifurcar nuestro código para que ocurra una cosa u otra.

```c
if (myCondicion) {
    // Hacemos algo
} else {
    // Hacemos otra cosa
}
```

#### 2. Estructura While

Un _While_ permite ejecutar código N cantidad de veces siempre y cuando una expresión se cumpla.

```c
while (myCondicion) {
    // ...
}
```

El contenido de la estructura _while_ se ejecutará mientras `myCondicion` sea verdadero.

#### 3. Ciclo for de iteración

Estructura muy similar a _while_, con la diferencia de que con _for_ se puede definir la cantidad de iteraciones que la estructura tendrá, o sea, la cantidad de veces que el código se ejecutará.

```c
for (uint i = 0; i < 10; i++) {
    // ...
}
```

En este ejemplo, el ciclo _for_ se ejecutará 10 veces, dado que hemos definido una variable que se autoincrementará en uno por cada iteración y, al cumplirse la condición, el _for_ termina.

### Conclusión

Estas son las estructuras básicas y con las que se construye la lógica en cualquier lenguaje de programación. Sin embargo, hay que considerar que entre más complejo sea un programa, esta lógica se puede tornar igual de compleja, con ciclos y condicionales anidados uno dentro de otro.

Es fácil perder el hilo de las instrucciones que se escriben conforme avanza un proyecto real, por lo que es recomendable mantener un orden y un código limpio.
