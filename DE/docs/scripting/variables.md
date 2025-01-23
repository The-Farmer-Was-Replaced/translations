# Variablen
Variablen können als benannte Container betrachtet werden, die einen Wert halten können.
Der Operator `=` wird verwendet, um eine Variable zu deklarieren und einen Wert darin zu speichern.

`variable_name = value`

Die linke Seite des Operators ist der Variablenname. Du kannst ihr jeden beliebigen Namen geben.
Die rechte Seite ist ein Ausdruck, dessen resultierender Wert in der Variable gespeichert wird.

Deklariere eine Variable namens `a` und speichere den Wert `5` darin:
`a = 5`
Deklariere eine Variable namens `b` und speichere den Rückgabewert von `can_harvest()` darin:
`b = can_harvest()`

Verwechsle den Operator `=` nicht mit dem Operator `==`.
Der Operator `==` überprüft, ob zwei Werte gleich sind und gibt `True` oder `False` zurück.
Der Operator `=` weist den Wert auf der rechten Seite dem Namen auf der linken Seite zu.

Nachdem einer Variable ein Wert zugewiesen wurde, kannst du sie im Code verwenden, um den enthaltenen Wert abzurufen

`a = 5
for i in range(a):
	do_a_flip()`

Die obige Schleife wird 5 Mal ausgeführt, weil `a` auf `5` gesetzt ist.
Das `i` in der `for`-Schleife ist ebenfalls eine Variable, der automatisch der aktuelle Wert der Sequenz bei jeder Iteration der Schleife zugewiesen wird. (Es muss nicht `i` genannt werden, du kannst ihr jeden gültigen Variablennamen geben.)

Variablen ermöglichen es auch, dasselbe mit einer while-Schleife zu tun:

`a = 5
i = 0
while i < a:
	do_a_flip()
	i = i + 1`

Dies macht dasselbe wie die for-Schleife oben. Wir müssen nur `i` manuell inkrementieren.
Beachte, dass wir `i` inkrementieren, indem wir es auf seinen eigenen Wert plus `1` setzen. Das Ändern des Wertes einer Variable basierend auf ihrem vorherigen Wert ist etwas sehr Häufiges.
Es kann mit diesen Operatoren abgekürzt werden: `+=, -=, *=, /=, %=`

`i = i + 1` ist dasselbe wie `i += 1`
`a = a / 3` ist dasselbe wie `a /= 3`
