# Trees
Bäume sind eine bessere Möglichkeit, Holz zu bekommen als Büsche. Sie geben jeweils 5 Holz. Wie Büsche können sie auf Gras oder Erde gepflanzt werden.

Bäume mögen etwas Platz und das Pflanzen direkt nebeneinander verlangsamt ihr Wachstum. Die Wachstumszeit verdoppelt sich für jeden Baum, der sich direkt nördlich, östlich, westlich oder südlich von ihm befindet. Wenn Sie also Bäume auf jedem Feld pflanzen, dauert es `2*2*2*2 = 16` Mal länger, bis sie wachsen.

<spoiler=anzeigen> Der `%` Operator kann hier nützlich sein. Denken Sie daran, dass der `%` Operator den Rest der Division zurückgibt. Gerade Zahlen, die durch `2` geteilt werden, haben einen Rest von `0` und ungerade Zahlen, die durch `2` geteilt werden, haben einen Rest von `1`.
Sie können also überprüfen, ob eine Zahl gerade ist, wie folgt:

`def ist_gerade(n):
	return n % 2 == 0`

Dies gibt `True` zurück, wenn n gerade ist, und `False`, wenn nicht.
</spoiler>
