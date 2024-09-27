# Costs
Jede Kostenangabe kann als ein Wörterbuch dargestellt werden, das Elemente auf Zahlen abbildet.

Die Funktion `get_cost()` gibt ein solches Wörterbuch zurück. Sie gibt den Preis an, um einen Artikel mit der Funktion `trade()` zu kaufen, das Saatgut, das benötigt wird, um eine Pflanze zu pflanzen, oder die Kosten für eine Freischaltung.

`get_cost(Items.Pumpkin_Seed)`
gibt `{Items.Carrot:1}` zurück

`get_cost(Entities.Pumpkin)`
gibt `{Items.Pumpkin_Seed:1}` zurück

`get_cost(Unlocks.Loops)`
gibt `{Items.Hay:5}` zurück

Für Upgrades, die bereits das maximale Level erreicht haben, gibt `get_cost()` `None` zurück.

Es kann so verwendet werden:
`cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]`
