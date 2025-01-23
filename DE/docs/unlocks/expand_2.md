# Erweitern 2
Dein Bauernhof hat sich erneut vergrößert! Die Felder sind nun nicht mehr in einer geraden Reihe, daher brauchst du eine Möglichkeit, ein quadratisches Raster zu durchqueren.

Mit der `while`-Schleife ist das nicht möglich, bis du Sinne und Operatoren freischaltest.
Es ist an der Zeit, die `for`-Schleife einzuführen.

Du kannst alles über die `for`-Schleife auf der Seite [For Loop](docs/scripting/for.md) nachlesen, aber fürs Erste brauchst du sie nur, um Code eine festgelegte Anzahl von Malen zu wiederholen.

`#do n flips
for i in range(5):
	do_a_flip()`

`range(n)` erstellt einen Zahlenbereich von `0` bis `n-1`, der `n` Elemente enthält. Die `for`-Schleife führt ihren Schleifenkörper einmal für jedes Element in der Sequenz aus. In diesem Beispiel wird `do_a_flip()` fünfmal aufgerufen.

Die Funktion `get_world_size()` ist jetzt auch verfügbar. Sie gibt die Kantenlänge deines Bauernhofs zurück, damit du Code schreiben kannst, der nicht mit der nächsten Erweiterung kaputtgeht.

`for i in range(get_world_size()):
	harvest()
	move(North)`

Dieses Beispiel erntet eine Spalte der Farm für jede Farmgröße.

Wenn du Schwierigkeiten hast, den Weg zu finden, um die Drohne über die Farm zu bewegen, siehe den Hinweis unten.
<spoiler=show hint>Es gibt natürlich mehrere Möglichkeiten, sich über die Farm zu bewegen.
Wir suchen nach einer Methode, sie systematisch zu durchlaufen, die nicht bei der nächsten Farmvergrößerung kaputtgeht.
Eine systematische Möglichkeit, jeden Platz zu erreichen, wäre, diese zwei Schritte ständig zu wiederholen:

1. Bewege dich mit `move(North)` bis du wieder an den Anfang kommst.
2. Bewege dich `East`.

`for i in range(get_world_size()):` kann hilfreich sein, um diese Idee in Code umzusetzen.
</spoiler>
<spoiler=show possible solution>Eine grundlegende Durchquerung könnte so aussehen:

`for i in range(get_world_size()):
	for j in range(get_world_size()):
		#do a flip on every tile
		do_a_flip()
		move(North)
	move(East)`
</spoiler>
