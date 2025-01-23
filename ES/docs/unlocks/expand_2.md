# Expandir 2
¡Tu granja se ha ampliado de nuevo! Ahora los cuadros ya no están en una sola fila, así que necesitas encontrar la forma de recorrer una cuadrícula.

Con el bucle `while` esto no es posible hasta que desbloquees sentidos y operadores.
Es momento de introducir el bucle `for`.

Puedes leer todo sobre el bucle `for` en la página [For Loop](docs/scripting/for.md), pero por ahora solo lo necesitarás para repetir código un número fijo de veces.

`#do n flips
for i in range(5):
	do_a_flip()`

`range(n)` crea un rango de números de `0` a `n-1` que contiene `n` elementos. El bucle `for` ejecuta su cuerpo una vez por cada elemento de la secuencia. En este ejemplo, `do_a_flip()` se llamará 5 veces.

Ahora también está disponible la función `get_world_size()`. Devuelve la longitud lateral de tu granja, para que tu código no se rompa con la próxima expansión.

`for i in range(get_world_size()):
	harvest()
	move(North)`

Este ejemplo cosecha una columna de la granja para cualquier tamaño de granja.

Si tienes problemas para averiguar cómo mover el dron por la granja, consulta la pista a continuación.
<spoiler=show hint>Existen varias maneras de desplazarse por la granja.
Buscamos una forma sistemática de recorrerla que no se rompa cuando la granja crezca de nuevo.
Una manera sistemática de llegar a cada lugar de la granja sería repetir los siguientes 2 pasos indefinidamente:

1. Muévete al `North` hasta que regreses al comienzo.
2. Muévete al `East`.

`for i in range(get_world_size()):` puede ayudar a transformar esta idea en código.
</spoiler>
<spoiler=show possible solution>Un recorrido básico podría ser así:

`for i in range(get_world_size()):
	for j in range(get_world_size()):
		#do a flip on every tile
		do_a_flip()
		move(North)
	move(East)`
</spoiler>
