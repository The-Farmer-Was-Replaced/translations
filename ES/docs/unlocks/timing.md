# Temporización
Si realmente quieres optimizar tus métodos, necesitas entender cómo se mide el tiempo en este juego. Este desbloqueo trata sobre eso.

## Nuevas Funciones
Hay dos funciones útiles para medir cuánto tardan las cosas:

`get_time()` devuelve el tiempo en segundos desde el inicio del juego.

`get_tick_count()` devuelve el número de ticks realizados desde el inicio de la ejecución.

Estas dos funciones, así como `quick_print()`, son completamente gratuitas. Incluso la operación de llamada es gratuita para ellas.

## Detalles de Ejecución

### Descargo de responsabilidad
Esto no es como funciona el rendimiento en el mundo real. Estas son solo reglas inventadas para este juego.
Probablemente solo te importará esto si quieres híper-optimizar tu código.

La unidad básica de tiempo para la ejecución del código se llama "tick". Sin mejoras de velocidad y energía, la ejecución procede a una velocidad de `400` ticks por segundo.

En general, las operaciones que combinan dos valores como `+, -, *, /, //, %, and, or, ...` toman un tick para ejecutarse.
El `-` de valor único y `not` son gratuitos.
Una rama `if` también toma un tick para ejecutarse (además del tiempo que toma evaluar la expresión de condición).
Las llamadas a funciones y las lecturas y escrituras de variables son gratuitas, pero las definiciones de funciones toman 1 tick.
Las declaraciones `import` son gratuitas.
Acceder a un módulo importado con el operador `.` es gratuito.
Si una función o módulo se ha pasado a través de argumentos o asignaciones de variables, usarlo costará 1 tick en lugar de 0.
Los bucles `for` y `while` toman un tick para comenzar, pero las iteraciones son gratuitas (sin contar el tiempo para evaluar las expresiones de condición/secuencia).
`return`, `break` y `continue` son todos gratuitos.
`pass` toma un tick, por lo que puede usarse para crear retrasos precisos.
La indexación en una estructura de datos toma un tick para el operador de índice y, en el caso de un diccionario o conjunto, ticks adicionales dependiendo del tamaño de la clave.

El número de ticks que las funciones incorporadas toman para ejecutarse está documentado en la documentación de cada función de manera individual.
