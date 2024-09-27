# Costs
Cualquier costo puede representarse como un diccionario que asigna elementos a números.

La función `get_cost()` devuelve dicho diccionario. Devuelve el precio para comprar un artículo usando la función `trade()`, la semilla requerida para plantar una planta, o el costo de un desbloqueo.

`get_cost(Items.Pumpkin_Seed)`
devuelve `{Items.Carrot:1}`

`get_cost(Entities.Pumpkin)`
devuelve `{Items.Pumpkin_Seed:1}`

`get_cost(Unlocks.Loops)`
devuelve `{Items.Hay:5}`

Para las mejoras que ya están al nivel máximo, `get_cost()` devolverá `None`.

Se puede usar así:
`cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]`
