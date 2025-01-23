# Árboles
Los [árboles](objects/tree) son una mejor manera de obtener madera que los arbustos. Dan 5 unidades de madera cada uno. Como los arbustos, se pueden plantar en hierba o tierra.

A los árboles les gusta tener espacio y plantarlos uno junto al otro ralentizará su crecimiento. El tiempo de crecimiento se duplica por cada árbol que esté en una casilla directamente al `North`, `East`, `West` o `South`. Así que si plantas árboles en cada casilla, tardarán `2*2*2*2 = 16` veces más en crecer.

<spoiler=mostrar> El operador `%` puede ser útil aquí. Recuerda que el operador `%` devuelve el resto de la división. Los números pares divididos por `2` tienen un resto de `0` y los números impares divididos por `2` tienen un resto de `1`.
Así puedes comprobar si un número es par:

`def is_even(n):
	return n % 2 == 0`

Esto devuelve `True` si n es par y `False` si no lo es.
</spoiler>
