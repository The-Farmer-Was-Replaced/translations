# For Loop
El bucle `for` funciona como en Python. (Llamado un bucle foreach en algunos lenguajes, no debe confundirse con el bucle estilo C, que es una cosa diferente).

`for i in sequence:
	#hacer algo con i`

Similar al bucle `while`, el bucle `for` también llama repetidamente a un bloque de código. En lugar de iterar basado en una condición, ejecuta el cuerpo del bucle una vez por cada elemento en una secuencia.

## Sintaxis
Un bucle for se ve así:

`for nombre_variable in secuencia:
	#bloque de código`

`nombre_variable` puede ser cualquier nombre que elijas. Es una variable que almacena el elemento actual en la secuencia. `secuencia` necesita ser algún valor que se pueda iterar como un rango o números. El bloque de código se ejecuta para cada elemento con la variable del bucle asignada a ese elemento.

## Secuencias
[Rangos](functions/range)      <unlock=lists>[Listas](docs/scripting/lists.md)      </unlock><unlock=functions>[Tuplas](docs/scripting/tuples.md)      </unlock><unlock=dicts>[Diccionarios](docs/scripting/dicts.md)      </unlock><unlock=sets>[Conjuntos](docs/scripting/sets.md)</unlock>

## Ejemplo
`for i in range(5):
	harvest()`

East bucle ejecuta el cuerpo un número fijo de veces. Es esencialmente lo mismo que escribir

`i = 0
harvest()
i = 1
harvest()
i = 2
harvest()
i = 3
harvest()
i = 4
harvest()`

Así que llama a `harvest()` 5 veces.

Véase también [Break](docs/scripting/break) y [Continue](docs/scripting/continue)
