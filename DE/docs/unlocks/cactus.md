# Kaktus
Wie andere Pflanzen können [Kakteen](objects/cactus) auf Boden angebaut und wie üblich geerntet werden.

Allerdings gibt es sie in verschiedenen Größen und mit einer seltsamen Ordnungsstruktur.

Wenn du einen vollständig gewachsenen Kaktus erntest und alle benachbarten Kakteen in sortierter Reihenfolge sind, werden alle benachbarten Kakteen rekursiv geerntet.

Ein Kaktus gilt als sortiert, wenn alle benachbarten Kakteen nach Norden und Osten vollständig gewachsen und größer oder gleich ihm sind und alle benachbarten Kakteen nach Süden und Westen vollständig gewachsen und kleiner oder gleich ihm sind.

Die Ernte breitet sich nur aus, wenn alle angrenzenden Kakteen vollständig gewachsen und in sortierter Reihenfolge sind.
Das bedeutet, dass wenn ein Quadrat aus gewachsenen Kakteen nach Größe sortiert ist und du einen Kaktus erntest, das gesamte Quadrat geerntet wird.

Du erhältst Kakteen entsprechend der Anzahl der geernteten Kakteen zum Quadrat. Wenn du also `n` Kakteen gleichzeitig erntest, erhältst du `n**2` `Items.Cactus`.

Die Größe eines Kaktus kann mit `measure()` gemessen werden.
Sie ist immer eine dieser Zahlen: `0,1,2,3,4,5,6,7,8,9`.

Du kannst auch eine Richtung in `measure(direction)` übergeben, um das benachbarte Feld in dieser Richtung der Drohne zu messen.

Du kannst einen Kaktus in jede Richtung mit seinem Nachbarn tauschen, indem du den `swap()` Befehl verwendest.
`swap(direction)` tauscht das Objekt unter der Drohne mit dem Objekt eine Kachel in der `direction` der Drohne.
