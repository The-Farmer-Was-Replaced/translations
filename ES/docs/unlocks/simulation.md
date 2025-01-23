# Simulación

Las simulaciones te permiten probar código rápidamente sin cambiar el estado de la granja real.
El estado inicial de la simulación puede elegirse libremente, y cuando la simulación termina, la granja real estará exactamente en el estado en que estaba antes de que comenzara la simulación.

La función `simulate()` se usa para iniciar una simulación.

El archivo donde debe comenzar la ejecución
`filename = "f1"`

Comenzar con todo desbloqueado y completamente mejorado
`sim_unlocks = Unlocks`

Comenzar con 10000 zanahorias y 50 heno
`sim_items = {Items.Carrot : 10000, Items.Hay : 50}`

Comenzar con una variable global "a" con un valor de 13
`sim_globals = {"a" : 13}`

Usar una semilla aleatoria fija
`seed = 0`

Acelerar la simulación por un factor de 64
`speedup = 64`

Ejecutar la simulación
`run_time = simulate(filename, sim_unlocks, sim_items, sim_globals, seed, speedup)`

La función `simulate()` devuelve el tiempo, en segundos, que tomó simular el archivo de inicio dado.

### Nombre del Archivo
El primer argumento de la función simulate es el nombre del archivo. Este es el nombre que se muestra en la parte superior de la ventana de código. La simulación ejecutará el archivo especificado como si hubieras hecho clic en el botón Ejecutar.

### Desbloqueos Iniciales
Todas las características de programación como bucles, declaraciones if, listas, diccionarios,... siempre permanecerán desbloqueadas.

El segundo argumento te permite especificar con qué desbloqueos/mejoras debe comenzar la simulación además de las características de programación. Debe ser una secuencia de desbloqueos. La simulación comenzará con todos los desbloqueos en la secuencia mejorados a su nivel máximo.

Si deseas especificar un nivel de mejora diferente al máximo, puedes pasar un diccionario que mapee los desbloqueos a niveles de desbloqueo. En este caso, los valores negativos corresponden al nivel máximo de desbloqueo.

### Elementos Iniciales
El tercer argumento te permite pasar un diccionario que mapea elementos a números. Especifica los elementos con los que comenzar la simulación.

### Variables Globales Iniciales
Debido a que la simulación inicia una ejecución de programa completamente nueva, no puedes acceder a variables del programa que inicia la simulación.
Sin embargo, es posible pasar valores a la simulación usando el cuarto argumento. Este es un diccionario que mapea nombres de variables en forma de cadenas a valores. Estas variables se agregan luego al alcance global de la ejecución dentro de la simulación.

Ten en cuenta que esto copia todos los valores, por lo que modificarlos dentro de la simulación no afectará los valores originales fuera de la simulación. No es posible devolver valores de la simulación más que el tiempo que tomó ejecutarla.

### Semilla Aleatoria
El quinto argumento te permite especificar la semilla aleatoria utilizada en la simulación. Debe ser un número entero positivo. Los valores negativos harán que se use una semilla aleatoria.

La semilla aleatoria afecta todo, desde los tiempos de crecimiento de las plantas hasta los diseños de laberintos y los tiempos de descomposición del agua. Si inicias la misma simulación varias veces con la misma semilla aleatoria y las mismas condiciones iniciales, el resultado siempre debería ser el mismo.

### Aceleración
El sexto argumento es la aceleración inicial de la simulación. Esto te permite probar cosas rápidamente. Si el juego no puede mantener la velocidad establecida, se ralentizará automáticamente.

La aceleración no afecta el resultado de la simulación de ninguna manera. Existe solo para reducir el tiempo de espera.
