# Tupel
Tupel sind eine großartige Möglichkeit, mehrere Werte in einem einzigen Wert zu kombinieren.
Um ein Tupel zu erstellen, trennen Sie die Werte einfach durch Kommas:

`tuple = 1, 2`

Sie können sie auch wieder in mehrere Variablen entpacken. Im folgenden Code wird das Tupel `(1,2)` in zwei Variablen `a` und `b` entpackt.

`a, b = 1, 2`

Tupel können wie Listen indexiert werden, sind jedoch unveränderlich und können nach der Erstellung nicht geändert werden.

`tuple = 1, 2`

`print(tuple[1])`
druckt `2`

`tuple[0] = 3`
löst einen Fehler aus

<unlock=dicts>
Im Gegensatz zu Listen können Tupel als Schlüssel in Dictionaries verwendet werden.

`d = {(1,2):(4,5)}

print(d[(1,2)])`
druckt `(4,5)`
</unlock>

Sie können auch nützlich sein, um mehrere Werte in einer Funktion zurückzugeben.

`def f():
    return 1, 2

a, b = f()`
