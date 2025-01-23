# Costos

Cualquier costo puede representarse como un diccionario que asigna elementos a números.

La función `get_cost()` devuelve dicho diccionario. Devuelve la semilla necesaria para plantar una planta o el costo de una desbloqueo.

`get_cost(Entities.Pumpkin)`

devuelve `{Items.Carrot:1}`

Para desbloqueos, se puede pasar un segundo argumento opcional para el nivel de desbloqueo del que deseas obtener el costo. Por defecto, es el nivel de desbloqueo actual.

`get_cost(Unlocks.Loops, 0)`

devuelve `{Items.Hay:5}`

Para desbloqueos que ya están en el nivel máximo, `get_cost()` devolverá `None`.

Se puede usar así:
`cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]`
