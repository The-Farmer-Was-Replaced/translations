# Break
`break` ermöglicht es, eine Schleife vorzeitig zu beenden. Wenn die `break`-Anweisung erreicht wird, wird die innerste Schleife sofort verlassen und der Code nach der Schleife wird ausgeführt.

`for i in range(10):
	break
print(i)`
Dies druckt `0`, weil `i` in der ersten Iteration der Schleife `0` ist und dann die `break`-Anweisung die Schleife beendet.

Es funktioniert auch bei `while`-Schleifen.

`while True:
	if can_harvest():
		break`

Dieser Code führt die `while`-Schleife aus, bis `can_harvest()` `True` ist.
Es hat den gleichen Effekt wie

`while not can_harvest():
	pass`

In verschachtelten Schleifen beendet `break` immer die innerste Schleife.

`for i in range(10):
	for j in range(10):
		break
		print("dies wird nie gedruckt")
	print("dies wird 10 mal gedruckt")`
