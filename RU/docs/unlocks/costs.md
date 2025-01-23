# Стоимость
Любая стоимость может быть представлена в виде словаря, который сопоставляет предметы с числами.

Функция `get_cost()` возвращает такой словарь. Она возвращает цену для покупки предмета с помощью функции `trade()`, семя для посадки растения или стоимость разблокировки.

Примеры:
`get_cost(Items.Pumpkin_Seed)`
вернет `{Items.Carrot:1}`

`get_cost(Entities.Pumpkin)`
вернет `{Items.Pumpkin_Seed:1}`

`get_cost(Unlocks.Loops)`
вернет `{Items.Hay:5}`

Для улучшений, которые уже достигли максимального уровня, `get_cost()` вернет `None`.

Пример использования:
```python
cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]
