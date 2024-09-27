# Lists
Listen sind eine einfache Möglichkeit, mehrere Werte in einer einzigen Variablen zu speichern.
Sie können neue Listen wie folgt erstellen:

`liste = [2, True, Items.Hay]`

Die Liste enthält nun die Werte `2`, `True` und `Items.Hay`.
Eine Liste kann auch leer sein:

`leere_liste = []`

Sie können auf ein Element einer Liste über seinen Index zugreifen. Der Index ist `0` für das erste Element, `1` für das zweite Element, `2` für das dritte...

pflanze Karotten
`liste = [Entities.Tree, Entities.Carrots, Entities.Pumpkin]
pflanze(liste[1])`

Sie können eine Liste mit einer for-Schleife durchlaufen. Das folgende Beispiel summiert alle Elemente in der Liste.

`liste = [4, 7, 2, 5]
summe = 0
for zahl in liste:
	summe += zahl`
`summe` ist jetzt `18`

Die folgenden Listenmethoden ermöglichen es Ihnen, Elemente hinzuzufügen und zu entfernen:

`liste.append(elem)` fügt ein Element am Ende der Liste hinzu:

`liste = [2, 6, 12]
liste.append(7)`
`liste` ist jetzt `[2, 6, 12, 7]`

`liste.remove(elem)` entfernt das erste Vorkommen eines Elements aus einer Liste:

`liste = [1, 2, 4, 2]
liste.remove(2)`
`liste` ist jetzt `[1, 4, 2]`

`liste.insert(index, elem)` fügt ein Element an der angegebenen Stelle ein:

`liste = [Entities.Tree, Items.Hay]
liste.insert(1, Items.Wood)`
`liste` ist jetzt `[Entities.Tree, Items.Wood, Items.Hay]`

`liste.pop(index)` entfernt das Element an der angegebenen Stelle.
Wenn kein Index angegeben ist, wird das letzte Element entfernt.

`liste = [3, 5, 8, 25]
liste.pop()`
`liste` ist jetzt `[3, 5, 8]`
`liste.pop(1)`
`liste` ist jetzt `[3, 8]`

Die Funktion `len()` gibt die Länge der Liste zurück.
`liste = [3, 2, 1]
x = len(liste)`
`x` ist jetzt `3`

Listen haben Referenzsemantik. Das bedeutet, dass das Zuweisen einer Liste zu einer Variablen das gleiche Listenobjekt dieser Variablen zuweist, anstatt eine Kopie der Liste zu erstellen.
Wenn zwei Variablen auf dieselbe Liste verweisen, werden Änderungen an der Liste von beiden gesehen.

`a = [1,2]
b = a
b.pop()`
`a` und `b` sind jetzt beide `[1]`

