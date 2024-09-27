# Cactus
Kakteen können auf Erde aus Kaktussamen angebaut werden.

Sie haben einen seltsamen Sinn für Gemeinschaft.

Wenn du einen Kaktus erntest, werden alle Kakteen auf dem Feld geerntet.
Die Anzahl der Kaktusgegenstände, die pro Kaktus fallen gelassen werden, entspricht der Weltgröße, wie sie von `get_world_size()` zurückgegeben wird.

Ein Kaktus lässt nur dann Kaktusgegenstände fallen, wenn er in sortierter Reihenfolge geerntet wird.
Ein Kaktus gilt als in sortierter Reihenfolge, wenn es einen kleineren oder gleich großen Kaktus im Süden und Westen und einen größeren oder gleich großen Kaktus im Norden und Osten gibt.
Im Wesentlichen müssen die Kakteen in aufsteigender x- und y-Richtung sortiert sein, damit sie etwas fallen lassen.

Wenn ein Kaktus am Rand des Feldes steht, müssen nur die vorhandenen benachbarten Felder korrekt sein, damit er als sortiert gilt.

Die Größe eines Kaktus kann mit `measure()` gemessen werden.
Sie ist immer eine dieser Zahlen: `0,1,2,3,4,5,6,7,8,9`.

Du kannst auch eine Richtung in `measure(dir)` übergeben, um das benachbarte Feld in dieser Richtung der Drohne zu messen.

Du kannst einen Kaktus mit seinem Nachbarn in jede Richtung mit dem Befehl `swap()` tauschen.
`swap(direction)` tauscht das Objekt unter der Drohne mit dem Objekt ein Feld in der `Richtung` der Drohne.

<spoiler=Hinweis anzeigen 1>
Wenn jede Spalte und jede Zeile des Feldes sortiert ist, dann sind alle Pflanzen in sortierter Reihenfolge.
</spoiler>
<spoiler=Hinweis anzeigen 2>
Du wirst für jeden Kaktus belohnt, der in sortierter Reihenfolge ist. Wenn einige Kakteen in sortierter Reihenfolge sind, erhältst du bereits einen Teil der Belohnung. Du musst nicht 100% sortieren.
</spoiler>
