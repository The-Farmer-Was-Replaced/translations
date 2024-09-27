# Expand 2
Dein Bauernhof hat sich wieder vergrößert! Jetzt sind die Felder nicht mehr in einer schönen Reihe, also musst du einen Weg finden, ein quadratisches Raster zu durchqueren.

Mit der `while`-Schleife ist dies nicht möglich, bis du Sinne und Operatoren freischaltest. Es ist Zeit, die `for`-Schleife einzuführen.

Du kannst alles über die `for`-Schleife auf der [For Loop](docs/scripting/for) Seite lesen, aber für jetzt wirst du sie nur brauchen, um Code eine feste Anzahl von Malen zu wiederholen.

`#mache n Flips
for i in range(5):
	do_a_flip()`

`range(n)` erstellt einen Bereich von Zahlen von `0` bis `n-1`, der `n` Elemente enthält. Die `for`-Schleife führt ihren Schleifenkörper einmal für jedes Element in der Sequenz aus. In diesem Beispiel wird `do_a_flip()` `5` Mal aufgerufen.

Die Funktion `get_world_size()` ist jetzt auch verfügbar. Sie gibt die Seitenlänge deines Bauernhofs zurück. Auf diese Weise kannst du Code schreiben, der beim nächsten Erweiterungs-Upgrade nicht kaputt geht.

`for i in range(get_world_size()):
	harvest()
	move(North)`

Dieses Beispiel erntet eine Spalte des Bauernhofs für jede Bauernhofgröße.

Wenn du Schwierigkeiten hast, herauszufinden, wie du die Drohne über den Bauernhof bewegen kannst, sieh dir den Hinweis unten an.
<spoiler=Hinweis anzeigen>Es gibt natürlich mehrere Möglichkeiten, sich auf dem Bauernhof zu bewegen.
Wir suchen nach einer Möglichkeit, ihn systematisch zu durchqueren, die nicht kaputt geht, wenn der Bauernhof wieder wächst.
Eine systematische Möglichkeit, jeden Ort auf dem Bauernhof zu erreichen, wäre, die folgenden 2 Schritte für immer zu wiederholen:

1. Bewege dich `North`, bis es zurückspringt.
2. Bewege dich `East`

`for i in range(get_world_size()):` könnte hilfreich sein, um diese Idee in Code umzusetzen.
</spoiler>
<spoiler=mögliche Lösung anzeigen> Die grundlegende Durchquerung könnte so aussehen:

`for i in range(get_world_size()):
	for j in range(get_world_size()):
		#mache einen Flip auf jedem Feld
		do_a_flip()
		move(North)
	move(East)`
</spoiler>
