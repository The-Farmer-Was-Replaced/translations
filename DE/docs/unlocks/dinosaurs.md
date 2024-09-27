# Dinosaurs
Dinosaurier sind alte, majestätische Kreaturen, die für antike Knochen gezüchtet werden können.

Um Dinosaurier zu bekommen, musst du Eier tauschen und sie mit `use_item(Items.Egg)` verwenden.

Dinosaurier bewegen sich gerne. Von Zeit zu Zeit wird der Dinosaurier mit einem zufälligen Nachbarn tauschen.
Dieser Tausch funktioniert genauso wie das manuelle Aufrufen von `swap(direction)`, außer dass es zufällig von Zeit zu Zeit passiert.

Dinosaurier können mit dem Befehl `harvest()` für Knochen geerntet werden.
Es gibt 4 verschiedene Arten von Dinosauriern.
Das Ernten eines Dinosauriers wird auch alle angrenzenden Dinosaurier derselben Art ernten, sodass eine gesamte verbundene Gruppe von Dinosauriern auf einmal geerntet wird.

Die Art eines Dinosauriers kann mit `measure()` gemessen werden. Dies wird eine eindeutige Nummer für jede Art von Dinosaurier zurückgeben.

Denke daran, dass du auch eine Richtung in measure übergeben kannst, um ein Wesen neben der Drohne zu messen.
`measure(North)` zum Beispiel wird das Wesen nördlich der Drohne messen.

Die Anzahl der Knochen, die du erhältst, hängt von der Größe der Gruppe der Dinosaurier ab, die du erntest. Das Ernten von Gruppen bis zu 4 wird Knochen in Höhe des Quadrats der Gruppengröße fallen lassen. Gruppen der Größe 4 oder größer lassen Knochen in Höhe des 4-fachen der Gruppengröße fallen.

Daher steigt die Anzahl der Knochen pro Dinosaurier mit der Gruppengröße bis zu einer Größe von 4 und bleibt dann konstant.
Für optimale Effizienz möchtest du immer Gruppen der Größe 4 oder größer ernten.

Gruppen wickeln sich auch um die Seite der Farm. Ein Dinosaurier am Rand der Farm wird als angrenzend an einen Dinosaurier auf der anderen Seite der Farm betrachtet.
