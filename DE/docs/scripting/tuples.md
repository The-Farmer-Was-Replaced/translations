# Tuples
Tupel sind eine großartige Möglichkeit, mehrere Werte zu einem einzigen Wert zu kombinieren.
Um ein Tupel zu erstellen, trennen Sie einfach die Werte mit Kommas:

`tuple = 1, 2`

Sie können sie auch wieder in mehrere Variablen entpacken. Im folgenden Code wird das Tupel `(1,2)` in zwei Variablen `a` und `b` entpackt.

`a, b = 1, 2`

Tupel können wie Listen indiziert werden, aber sie sind unveränderlich und können nach der Erstellung nicht geändert werden.

`tuple = 1, 2`

`print(tuple[1])`
druckt `2`

`tuple[0] = 3`
wirft einen Fehler
<unlock=dicts>
Im Gegensatz zu Listen können Tupel als Schlüssel in Wörterbüchern verwendet werden.

`d = {(1,2):(4,5)}

print(d[(1,2)])`
druckt `(4,5)`</unlock>

Sie können auch nützlich sein, um mehrere Werte in einer Funktion zurückzugeben.

`def f():
    return 1, 2

a, b = f()`
