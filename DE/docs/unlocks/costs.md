# Kosten

Jede Kostenart kann als Wörterbuch dargestellt werden, das Gegenstände auf Zahlen abbildet.

Die Funktion `get_cost()` gibt ein solches Wörterbuch zurück. Sie gibt den Saatgutbedarf zum Pflanzen einer Pflanze oder die Kosten eines Freischaltens zurück.

`get_cost(Entities.Pumpkin)`

gibt `{Items.Carrot:1}` zurück

Für Freischaltungen kann ein optionales zweites Argument übergeben werden, um die Kosten für das gewünschte Freischaltlevel zu erhalten. Standardmäßig ist es das aktuelle Freischaltlevel.

`get_cost(Unlocks.Loops, 0)`

gibt `{Items.Hay:5}` zurück

Für Freischaltungen, die bereits das maximale Level erreicht haben, gibt `get_cost()` `None` zurück.

Es kann wie folgt verwendet werden:
`cost = get_cost(something)
for item in cost:
	amount_of_this_item_needed = cost[item]`
