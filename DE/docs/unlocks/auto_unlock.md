# Automatisches Freischalten
Um das Spiel vollständig zu automatisieren, kannst du die `unlock()` Funktion verwenden, um Funktionen automatisch freizuschalten.
Zum Beispiel kannst du `unlock(Unlocks.Speed)` und `unlock(Unlocks.Expand)` verwenden, um die Geschwindigkeits- und Erweiterungsfunktionen freizuschalten.

Um die Kosten eines Freischaltens zu bestimmen, verwende einfach die `get_cost()` Funktion wie bei einer Pflanze oder einem Gegenstand.
Beispiel:
`get_cost(Unlocks.Loops)`
gibt `{Items.Hay:5}` zurück

Wenn du herausfinden möchtest, wie viele von einem bestimmten Freischalten du hast, verwende die `num_unlocked(unlock)` Funktion.

Zum Beispiel, `num_unlocked(Unlocks.Speed)` gibt die Anzahl der Geschwindigkeit-Upgrades zurück, die du hast.

`num_unlocked(Unlocks.Senses)` gibt `1` zurück, wenn Sinne freigeschaltet sind, und `0`, wenn sie es nicht sind.

Du kannst `num_unlocked()` auch auf Items, Entities oder Grounds verwenden. Dies gibt `1` zurück, wenn es freigeschaltet ist, andernfalls `0`.

Sei vorsichtig `num_unlocked(Unlocks.Carrots)` gibt die Anzahl der Male zurück, die es freigeschaltet/upgegradet wurde.
`num_unlocked(Items.Carrot)` gibt nur `0` oder `1` zurück. (Gleiches gilt für andere Pflanzen)
