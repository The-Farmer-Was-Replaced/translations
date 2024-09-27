# Speed Upgrade
Die Ausführungsgeschwindigkeit wurde verdoppelt. Das Problem ist, dass die Drohne jetzt schneller erntet, als das Gras wachsen kann, was zu keiner Ernte führt. Um dies zu bewältigen, sind jetzt [if](docs/scripting/if)-Verzweigungen und die Funktion [can_harvest](functions/can_harvest) freigeschaltet.

## Vor dem Ernten prüfen
Bisher hatten wir nur `True` und `False` als Bedingungen, was natürlich nicht sehr nützlich mit `if` ist.

Die neue Funktion `can_harvest()` bietet eine bessere Bedingung. `can_harvest()` gibt `True` zurück, wenn die Pflanze unter der Drohne geerntet werden kann, und `False` andernfalls.

`if can_harvest():
	#do something`

Der Grund, warum Sie diese Funktion als Bedingung verwenden können, liegt darin, dass sie einen booleschen Wert zurückgibt.

Ein Rückgabewert bedeutet im Wesentlichen, dass nach der Ausführung der Funktion der Funktionsaufrufausdruck zum zurückgegebenen Wert ausgewertet wird.

Was passiert, wenn der obige Code ausgeführt wird:
	-das if wird ausgeführt
	-`can_harvest()` wird aufgerufen
	-`can_harvest()` führt seine Aufgabe aus
	-`can_harvest()` gibt `True` oder `False` zurück
	-die Anweisung lautet nun `if True:` oder `if False:`
	-die Drohne macht einen Flip, wenn sie ernten kann

Jetzt können wir `if` verwenden, um zu verhindern, dass die Drohne zu früh erntet.
