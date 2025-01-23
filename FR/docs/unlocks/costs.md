# Coûts

Tout coût peut être représenté comme un dictionnaire qui associe des éléments à des nombres.

La fonction `get_cost()` retourne un tel dictionnaire. Elle retourne la graine nécessaire pour planter une plante ou le coût d'un déblocage.

`get_cost(Entities.Pumpkin)`

retourne `{Items.Carrot:1}`

Pour les déblocages, un deuxième argument optionnel peut être passé pour le niveau de déblocage dont vous souhaitez obtenir le coût. Par défaut, c'est le niveau de déblocage actuel.

`get_cost(Unlocks.Loops, 0)`

retourne `{Items.Hay:5}`

Pour les déblocages qui sont déjà au niveau maximum, `get_cost()` retournera `None`.

Cela peut être utilisé comme ceci :
`cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]`
