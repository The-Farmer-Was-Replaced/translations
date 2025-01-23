# Continue

`continue` ermöglicht es, die aktuelle Iteration einer Schleife zu stoppen und zur nächsten Iteration der innersten Schleife zu springen.

`for i in range(10):
	continue
    print("dies wird niemals gedruckt")`

Dies führt alle `10` Iterationen der Schleife aus, aber die `print`-Anweisung nach dem `continue` wird immer übersprungen.

Es funktioniert auch mit `while`-Schleifen.

`while True:
	if not can_harvest():
		continue

	harvest()`

Dieser Code ruft `harvest()` nur auf, wenn `can_harvest()` `True` ist.
Es hat die gleiche Wirkung wie

`while True:
	if can_harvest():
		harvest()`

In verschachtelten Schleifen beeinflusst `continue` immer die innerste Schleife.

`for i in range(10):
	for j in range(10):
	    print("dies wird 100 Mal gedruckt")
		continue
		print("dies wird niemals gedruckt")
	print("dies wird 10 Mal gedruckt")`
