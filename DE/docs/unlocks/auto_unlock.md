# Auto Unlocks
Um das Spiel vollständig zu automatisieren, können Sie die Funktion `unlock()` verwenden, um Funktionen automatisch freizuschalten.
Zum Beispiel können Sie `unlock(Unlocks.Speed)` und `unlock(Unlocks.Expand)` verwenden, um die Geschwindigkeits- und Erweiterungsfunktionen freizuschalten.

Um die Kosten einer Freischaltung zu bestimmen, verwenden Sie einfach die Funktion `get_cost()`, wie Sie es für eine Pflanze oder ein Objekt tun würden.
Beispiel:
`get_cost(Unlocks.Loops)`
gibt `{Items.Hay:5}` zurück.

Wenn Sie herausfinden möchten, wie viele einer bestimmten Freischaltung Sie haben, verwenden Sie die Funktion `num_unlocked(unlock)`.

Zum Beispiel wird `num_unlocked(Unlocks.Speed)` die Anzahl der Geschwindigkeits-Upgrades zurückgeben, die Sie haben.

`num_unlocked(Unlocks.Senses)` gibt `1` zurück, wenn die Sinne freigeschaltet sind, und `0`, wenn sie nicht freigeschaltet sind.

Sie können `num_unlocked()` auch auf Items, Entities oder Grounds anwenden. Dies wird `1` zurückgeben, wenn es freigeschaltet ist, andernfalls `0`.

Seien Sie vorsichtig, `num_unlocked(Unlocks.Carrots)` gibt die Anzahl der Male zurück, die es freigeschaltet/aufgerüstet wurde.
`num_unlocked(Items.Carrots)` gibt nur `0` oder `1` zurück. (Gleiches gilt für andere Pflanzen)
