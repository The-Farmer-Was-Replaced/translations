# Watering
Pflanzen wachsen schneller, wenn sie bewässert werden. Der Boden hat einen Wasserstand, der von `0` bis `1` reicht.
Die Funktion `get_water()` gibt den Wasserstand des Bodens zurück, über dem sie sich befindet.

Die Wachstumsgeschwindigkeit einer Pflanze, die auf bearbeitetem Boden wächst, steigt linear von 1x Geschwindigkeit bei Wasserstand 0 auf 5x Geschwindigkeit bei Wasserstand 1.
Bewässerung beeinflusst nur Pflanzen, die auf bearbeitetem Boden wachsen. Sie hat keine Auswirkungen auf Pflanzen, die auf Rasen wachsen.

Der Boden trocknet mit der Zeit aus: Das Wasser verliert ab und zu 1% seines aktuellen Wasserstands. Den Wasserstand hoch zu halten, verbraucht viel mehr Wasser als ihn niedrig zu halten.

Sie können Wassertanks verwenden, um Ihre Pflanzen zu bewässern. Sie können leere Tanks mit Holz kaufen, indem Sie `trade(Items.Empty_Tank)` verwenden.

Ein Tank kann `0,25` Wasser halten.

Tanks füllen sich automatisch. Die Füllrate beträgt `0,5`% der Anzahl der leeren Tanks pro Sekunde. Wenn Sie also `100` leere Tanks haben, wird einer von ihnen alle `2` Sekunden gefüllt.

Rufen Sie `use_item(Items.Water_Tank)` über jedem Boden auf, um einen Tank zu entleeren und den Boden zu bewässern.
