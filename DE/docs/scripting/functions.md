# Functions
Verwenden Sie das Schlüsselwort `def`, um eine neue Funktion zu definieren:
`def f(arg1, arg2 = False):
	#Funktionscode`

Sie können den Aufrufoperator `()` verwenden, um die Funktion aufzurufen:
`f(42)`

Im Gegensatz zu Python können Funktionen, die im globalen Bereich einer beliebigen geöffneten Datei definiert sind, durch ihren Namen aufgerufen werden, auch wenn die `def`-Anweisung nie ausgeführt wurde.
Weitere Informationen finden Sie unter [Scopes](docs/scripting/scopes.md).

## Einführung
Sie haben bereits eingebaute Funktionen wie `harvest()` gesehen.
Sie können auch Ihre eigenen Funktionen definieren, was es ermöglicht, Ihren Code modular zu strukturieren. Es ermöglicht Ihnen im Grunde, einem Codeblock einen Namen zu geben, sodass Sie ihn von überall aus aufrufen können.

## Funktionsdefinitionen
Zum Beispiel könnten Sie eine Funktion definieren, die die Drohne mehrmals bewegt.

`def move_n_dir(n, dir):
	for i in range(n):
		move(dir)`

Das Schlüsselwort `def` signalisiert, dass dies eine Funktionsdefinition ist.
`move_n_dir` ist der Name, an den die Funktion gebunden wird. Dies kann jeder gültige Variablenname sein und wird verwendet, um die Funktion aufzurufen.
`n` und `dir` sind Parameter. Sie sind Variablen, die die Werte enthalten, die an die Funktion übergeben werden (Diese Werte werden auch Argumente genannt). Sie können einer Funktionsdefinition so viele Parameter hinzufügen, wie Sie möchten.
Nach dem `:` folgt der Codeblock, der ausgeführt wird, wenn die Funktion aufgerufen wird.

Mit der obigen Definition bewegt der folgende Code die Drohne `10` Felder nach `Norden` und `2` Felder nach `Westen`.

`move_n_dir(10, Norden)
move_n_dir(2, Westen)`

## Rückgabewerte
Verwenden Sie das Schlüsselwort `return`, um eine Funktion einen Wert zurückgeben zu lassen.
Zum Beispiel definiert die folgende Funktion die exklusive Oder-Operation. Die exklusive Oder gibt `True` zurück, wenn ein Wert `True` ist und der andere `False`:

`def xor(a, b):
	return a != b

if xor(True, False):
	do_a_flip()`

[Tuples](docs/scripting/tuples.md) ermöglichen die Rückgabe mehrerer Werte.

## Standardargumente
Sie können auch Standardwerte zuweisen, die verwendet werden, wenn keine Argumente übergeben werden.

`def f(a = False):
	if a:
		do_a_flip()

f()

f(True)`

Ein Argument, das einen Standardwert hat, kann nicht von einem Argument gefolgt werden, das keinen Standardwert hat.

## Erweiterte Funktionsnutzung
Funktionen sind Werte wie jeder andere Wert auch, und die `def`-Anweisung wirkt einfach wie eine Zuweisungsanweisung, die die Funktion dem Namen zuweist, den Sie ihr geben.
Dies ermöglicht Dinge wie:

`def f():
	def d():
		do_a_flip()
	return d

f()()`

Hier ruft `f()` die Funktion `f` auf, die eine neue Funktion `d` definiert und zurückgibt. Das zweite `()` führt dann die zurückgegebene Funktion aus und führt einen Flip aus.
(Diese Art von Dingen zu tun, ist normalerweise keine gute Idee, weil es schwer zu erkennen ist, was vor sich geht)

Funktionen, die andere Funktionen als Argumente nehmen, lassen Sie wirklich kreativ werden:

`def f(g, arg):
	for _ in range(10):
		g(arg)

f(move, Norden)
f(use_item, Items.Fertilizer)`

Dieser Code bewegt die Drohne `10` Mal nach `Norden` und verwendet dann `10` Mal Dünger.
