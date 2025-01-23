# Erweitern 1
<unlock=for>Siehe auch [Expand_2](docs/unlocks/expand_2.md)

</unlock>Dein Bauernhof ist gewachsen! Dieser Platz nützt nicht viel, wenn du die Drohne nicht bewegen kannst, daher gibt es eine neue Funktion `move()`, die die Drohne bewegt. `move()` erfordert, dass du die Richtung angibst, in die sich die Drohne bewegen soll. Es gibt vier neue Konstanten dafür: `North, East, South, West`.

Beispielsweise bewegt `move(North)` die Drohne ein Feld nach Norden.

Wenn du über den Rand der Farm hinausfliegst, wird die Drohne wieder auf der anderen Seite platziert.
Der folgende Beispielcode bewegt sich unendlich nach Norden und springt zum Anfang zurück, wenn er den Rand erreicht:

`while True:
	move(North)`
