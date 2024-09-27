# Benchmark
Hay dos funciones útiles para medir cuánto tiempo toman las cosas:

`get_time()` devuelve el tiempo en segundos desde el inicio del juego.

`get_op_count()` devuelve el número de operaciones realizadas desde el inicio de la ejecución.

La mayoría de las acciones toman un número constante de operaciones, y mientras el factor de velocidad permanezca igual, el tiempo por operación también es constante.

Las acciones que no afectan al dron, como leer variables y llamar a funciones, cuentan como `1` operación. (Llamar a una función generalmente consiste en leer la función desde una variable y luego llamarla, por lo que son `2` operaciones)

Las acciones del dron como plantar, cosechar o moverse cuentan como `200` operaciones.

Tenga en cuenta que el rendimiento en el mundo real es mucho más complejo que esto. Los conteos de operaciones consistentes como este son una simplificación hecha para este juego.
