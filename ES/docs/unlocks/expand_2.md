# Expand 2
¡Tu granja se ha expandido de nuevo! Ahora las parcelas ya no están en una fila ordenada, por lo que necesitas encontrar una manera de recorrer una cuadrícula.

Con el bucle `while` esto no es posible hasta que desbloquees sentidos y operadores.
Es hora de introducir el bucle `for`.

Puedes leer todo sobre el bucle `for` en la página [Bucle For](docs/scripting/for), pero por ahora solo lo necesitarás para repetir código un número fijo de veces.

`#hacer n volteretas
for i in range(5):
	hacer_una_voltereta()`

`range(n)` crea un rango de números desde `0` hasta `n-1` que tiene `n` elementos. El bucle `for` ejecuta su cuerpo de bucle una vez por cada elemento en la secuencia. En este ejemplo, `hacer_una_voltereta()` se llamará `5` veces.

La función `get_world_size()` también está disponible ahora. Devuelve la longitud del lado de tu granja. De esta manera, puedes escribir código que no se rompa con la próxima actualización de expansión.

`for i in range(get_world_size()):
	harvest()
	move(North)`

East ejemplo cosecha una columna de la granja para cualquier tamaño de granja.

Si estás atascado tratando de averiguar cómo mover el dron por la granja, consulta la pista a continuación.
<spoiler=mostrar pista>Hay, por supuesto, varias formas de moverse por la granja.
Lo que estamos buscando es una manera de recorrerla de una manera sistemática que no se rompa cuando la granja crezca de nuevo.
Una manera sistemática de llegar a cada lugar de la granja sería repetir los siguientes 2 pasos para siempre:

1. Moverse al `North` hasta que vuelva a empezar.
2. Moverse al `East`

`for i in range(get_world_size()):` puede ser útil para convertir esta idea en código.
</spoiler>
<spoiler=mostrar posible solución> La travesía básica podría verse así:

`for i in range(get_world_size()):
	for j in range(get_world_size()):
		#hacer una voltereta en cada parcela
		hacer_una_voltereta()
		move(North)
	move(East)`
</spoiler>
