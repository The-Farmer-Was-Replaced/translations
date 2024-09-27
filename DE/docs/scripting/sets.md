# Sets
Mengen sind wie [Wörterbücher](docs/scripting/dicts), aber ohne Werte. Sie sind nur eine ungeordnete Menge von Schlüsseln.

Sie werden wie Wörterbücher erstellt, aber ohne Werte.
`set = {Nord, Ost, West}`

Verwenden Sie `set.add(elem)`, um ein neues Element zur Menge hinzuzufügen.

Verwenden Sie `set.remove(elem)`, um ein Element aus der Menge zu entfernen.

Verwenden Sie `if elem in set:`, um zu überprüfen, ob die Menge ein Element enthält.

Verwenden Sie `for elem in set:`, um alle Elemente in der Menge zu durchlaufen.
Für größere Mengen ist der `in` Operator viel schneller als bei einer Liste.

Genau wie Wörterbücher sind Mengen ungeordnet, daher gibt es keine Garantien über die Reihenfolge, in der die Elemente durchlaufen werden.

Außerdem sind Elemente in Mengen einzigartig, sodass das Hinzufügen eines bereits vorhandenen Elements die Menge nicht verändert.
