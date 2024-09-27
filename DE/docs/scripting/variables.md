# Variables
Variablen können als benannte Container betrachtet werden, die einen Wert enthalten können.
Der `=` Operator wird verwendet, um eine Variable zu deklarieren und einen Wert darin zu speichern.

`variablen_name = wert`

Die linke Seite des Operators ist der Variablenname. Sie können ihm jeden beliebigen Namen geben.
Die rechte Seite ist ein Ausdruck, dessen resultierender Wert in der Variablen gespeichert wird.

Deklarieren Sie eine Variable namens `a` und speichern Sie den Wert `5` darin:
`a = 5`
Deklarieren Sie eine Variable namens `b` und speichern Sie den Rückgabewert von `can_harvest()` darin:
`b = can_harvest()`

Verwechseln Sie nicht den `=` Operator mit dem `==` Operator.
Der `==` Operator überprüft, ob zwei Werte gleich sind, und gibt `True` oder `False` zurück.
Der `=` Operator weist den Wert auf der rechten Seite dem Namen auf der linken Seite zu.

Nachdem eine Variable zugewiesen wurde, können Sie sie im Code verwenden, um den darin enthaltenen Wert abzurufen.

`a = 5
for i in range(a):
	do_a_flip()`

Die obige Schleife wird 5 Mal ausgeführt, weil `a` auf `5` gesetzt ist.
Das `i` in der `for` Schleife ist ebenfalls eine Variable, die automatisch bei jeder Iteration der Schleife den aktuellen Wert der Sequenz zugewiesen bekommt. (Es muss nicht `i` genannt werden, Sie können ihm jeden gültigen Variablennamen geben.)

Variablen ermöglichen es Ihnen auch, dasselbe mit einer while-Schleife zu tun:

`a = 5
i = 0
while i < a:
	do_a_flip()
	i = i + 1`

Dies tut dasselbe wie die obige for-Schleife. Wir müssen `i` nur manuell inkrementieren.
Beachten Sie, dass wir `i` inkrementieren, indem wir es auf seinen eigenen Wert plus `1` setzen. Das Ändern des Wertes einer Variablen basierend auf ihrem vorherigen Wert ist sehr häufig.
Es kann mit diesen Operatoren abgekürzt werden: `+=, -=, *=, /=, %=`

`i = i + 1` ist dasselbe wie `i += 1`
`a = a / 3` ist dasselbe wie `a /= 3`

