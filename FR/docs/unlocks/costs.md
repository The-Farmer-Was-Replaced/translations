# Coûts

Tout coût peut être représenté comme un dictionnaire qui associe des objets à des nombres.

La fonction `get_cost()` renvoie un tel dictionnaire. Elle retourne le prix pour acheter un objet en utilisant la fonction `trade()`, la graine nécessaire pour planter une plante, ou le coût d'un déblocage.

`get_cost(Items.Pumpkin_Seed)`
renvoie `{Items.Carrot:1}`

`get_cost(Entities.Pumpkin)`
renvoie `{Items.Pumpkin_Seed:1}`

`get_cost(Unlocks.Loops)`
renvoie `{Items.Hay:5}`

Pour les améliorations qui sont déjà au niveau maximum, `get_cost()` retournera `None`.

Elle peut être utilisée comme ceci :
`cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]`