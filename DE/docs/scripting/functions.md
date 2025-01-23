# Funktionen
Verwende das Schlüsselwort `def`, um eine neue Funktion zu definieren:
`def f(arg1, arg2 = False):
	#function code`

Du kannst den Aufrufoperator `()` verwenden, um die Funktion aufzurufen:
`f(42)`

Siehe auch [Scopes](docs/scripting/scopes.md), um mehr über lokale und globale Variablen in Funktionen zu erfahren.

## Einführung
Du hast bereits eingebaute Funktionen wie `harvest()` gesehen.
Du kannst auch eigene Funktionen definieren, was es ermöglicht, deinen Code modular zu strukturieren. Es erlaubt dir im Grunde, einem Codeblock einen Namen zu geben, sodass du ihn von überall aufrufen kannst.

## Funktionsdefinitionen
Zum Beispiel könntest du eine Funktion definieren, die die Drohne mehrmals bewegt.

`def move_n_dir(n, dir):
	for i in range(n):
		move(dir)`

Das Schlüsselwort `def` signalisiert, dass dies eine Funktionsdefinition ist.
`move_n_dir` ist der Name, mit dem die Funktion gebunden wird. Dies kann jeder gültige Variablenname sein und wird verwendet, um die Funktion aufzurufen.
`n` und `dir` sind Parameter. Sie sind Variablen, die die Werte halten, die an die Funktion übergeben werden (Diese Werte werden auch Argumente genannt). Du kannst so viele Parameter zu einer Funktionsdefinition hinzufügen, wie du möchtest.
Nach dem `:` folgt der Codeblock, der ausgeführt wird, wenn die Funktion aufgerufen wird.

Mit der obigen Definition bewegt folgender Code die Drohne `10` Kacheln `North` und `2` Kacheln `West`.

`move_n_dir(10, North)
move_n_dir(2, West)`

Wenn du `def function():` siehst, solltest du wirklich daran denken, dass es sich um eine Variablenzuweisung wie diese handelt:
`function = create_new_function_object()`
Wie bei allen Zuweisungen kannst du die Variable nicht verwenden, bevor sie zugewiesen wurde!
Die `def`-Anweisung muss ausgeführt werden, bevor irgendwelche Funktionsaufrufe stattfinden.
Das funktioniert nicht:

`func()
def func():
	pass`

## Rückgabewerte
Verwende das Schlüsselwort `return`, um eine Funktion einen Wert zurückgeben zu lassen.
Zum Beispiel definiert die folgende Funktion die exklusive Oder-Operation. Das exklusive Oder gibt `True` zurück, wenn ein Wert `True` und der andere `False` ist:

`def xor(a, b):
	return a != b

if xor(True, False):
	do_a_flip()`

[Tuples](docs/scripting/tuples.md) ermöglichen das Zurückgeben mehrerer Werte.

## Standardargumente
Du kannst auch Standardwerte zuweisen, die verwendet werden, wenn keine Argumente übergeben werden.

`def f(a = False):
	if a:
		do_a_flip()

f()

f(True)`

Ein Argument, das einen Standardwert hat, kann nicht von einem Argument gefolgt werden, das keinen Standardwert hat.

## Fortgeschrittene Funktionsnutzung
Funktionen sind Werte, genau wie jeder andere Wert, und die `def`-Anweisung verhält sich wie eine Zuweisungsanweisung, die die Funktion an den von dir gegebenen Namen bindet.
Dies ermöglicht es, Dinge wie das Folgende zu tun:

`def f():
	def d():
		do_a_flip()
	return d

f()()`

Hier ruft `f()` die Funktion `f` auf, die eine neue Funktion `d` definiert und zurückgibt. Die zweiten `()` führen dann die zurückgegebene Funktion aus und führen den Flip aus.
(Diese Art von Dingen zu tun, ist normalerweise keine gute Idee, weil es schwer zu sehen ist, was vor sich geht)

Funktionen, die andere Funktionen als Argumente nehmen, lassen dich wirklich kreativ werden:

`def f(g, arg):
	for _ in range(10):
		g(arg)

f(move, North)
f(use_item, Items.Fertilizer)`

Dieser Code bewegt die Drohne `North` 10 Mal und verwendet dann Dünger 10 Mal.
