# Bäume
[Bäume](objects/tree) sind eine bessere Möglichkeit, Holz zu bekommen als Büsche. Sie geben jeweils 5 Holz. Wie Büsche können sie auf Gras oder Erde gepflanzt werden.

Bäume brauchen etwas Platz und wenn sie direkt nebeneinander gepflanzt werden, verlangsamt sich ihr Wachstum. Die Wachstumszeit verdoppelt sich für jeden Baum, der sich direkt `North`, `East`, `West` oder `South` davon befindet. Wenn Sie also Bäume auf jeder Kachel pflanzen, dauert es `2*2*2*2 = 16` mal länger, bis sie wachsen.

<spoiler=zeigen> Der `%`-Operator kann hier nützlich sein. Denken Sie daran, dass der `%`-Operator den Rest der Division zurückgibt. Gerade Zahlen durch `2` geteilt haben einen Rest von `0` und ungerade Zahlen durch `2` geteilt haben einen Rest von `1`.
Sie können also prüfen, ob eine Zahl gerade ist:

`def is_even(n):
	return n % 2 == 0`

Dies gibt `True` zurück, wenn n gerade ist, und `False`, wenn nicht.
</spoiler>
