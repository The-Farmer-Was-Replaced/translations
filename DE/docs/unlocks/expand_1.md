# Expand 1
Dein Bauernhof ist gewachsen! Dieser Raum ist nicht sehr nützlich, wenn du die Drohne nicht bewegen kannst, daher gibt es eine neue Funktion `move()`, die die Drohne bewegt. `move()` erfordert, dass du die Richtung angibst, in die du die Drohne bewegen möchtest. Es gibt vier neue Konstanten dafür: `North, East, South, West`.

Zum Beispiel wird `move(North)` die Drohne ein Feld nach Norden bewegen.

Wenn du über den Rand des Bauernhofs hinausgehst, wird die Drohne auf die andere Seite des Bauernhofs bewegt.
Der folgende Beispielcode wird die Drohne immer weiter nach Norden bewegen und zurück zum Anfang springen, wenn sie den Rand des Bauernhofs erreicht:

`while True:
	move(North)`
