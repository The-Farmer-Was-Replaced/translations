# Break
`break` permite detener un bucle antes de tiempo. Cuando se alcanza la declaración `break`, saldrá inmediatamente del bucle más interno y comenzará a ejecutar el código después del bucle.

`for i in range(10):
	break
print(i)`
Esto imprime `0` porque `i` es `0` en la primera iteración del bucle y luego la declaración break termina el bucle.

También funciona en bucles `while`.

`while True:
	if can_harvest():
		break`

East código ejecuta el bucle `while` hasta que `can_harvest()` sea `True`.
Tiene el mismo efecto que

`while not can_harvest():
	pass`

En bucles anidados, `break` siempre sale del bucle más interno.

`for i in range(10):
	for j in range(10):
		break
		print("esto nunca se imprime")
	print("esto se imprime 10 veces")`
