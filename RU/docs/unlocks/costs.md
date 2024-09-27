# Costs
Любая стоимость может быть представлена как словарь, который отображает предметы на числа.

Функция `get_cost()` возвращает такой словарь. Она возвращает цену покупки предмета с использованием функции `trade()`, семена, необходимые для посадки растения, или стоимость разблокировки.

`get_cost(Items.Pumpkin_Seed)`
возвращает `{Items.Carrot:1}`

`get_cost(Entities.Pumpkin)`
возвращает `{Items.Pumpkin_Seed:1}`

`get_cost(Unlocks.Loops)`
возвращает `{Items.Hay:5}`

Для улучшений, которые уже достигли максимального уровня, `get_cost()` вернет `None`.

Ее можно использовать следующим образом:
`cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]`
