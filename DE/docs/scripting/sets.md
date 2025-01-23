# Mengen
Mengen sind wie [Dictionaries](docs/scripting/dicts.md), aber ohne Werte. Sie sind einfach eine ungeordnete Menge von Schlüsseln.

Sie werden wie Dictionaries erstellt, jedoch ohne Werte.
`set = {North, East, West}`

Verwenden Sie `set()`, um eine leere Menge zu erstellen. Beachten Sie, dass `{}` ein leeres Dictionary erstellt.

Verwenden Sie `set.add(elem)`, um ein neues Element zur Menge hinzuzufügen.

Verwenden Sie `set.remove(elem)`, um ein Element aus einer Menge zu entfernen.

Verwenden Sie `if elem in set:`, um zu überprüfen, ob die Menge ein Element enthält.

Verwenden Sie `for elem in set:`, um alle Elemente in der Menge zu iterieren.
Für größere Mengen ist der `in` Operator viel schneller als bei einer Liste.

Wie bei Dictionaries sind Mengen ungeordnet, sodass es keine Garantien über die Reihenfolge gibt, in der die Elemente iteriert werden.

Außerdem sind die Elemente in Mengen einzigartig, sodass das Hinzufügen eines bereits in der Menge vorhandenen Elements die Menge nicht ändert.
