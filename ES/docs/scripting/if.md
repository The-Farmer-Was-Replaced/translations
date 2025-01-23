# Si
Puedes usar `if`, `elif` y `else` para ejecutar código condicionalmente.

`if condition1:
	do_a_flip()
elif condition2:
	harvest()
else:
	do_a_flip()
	harvest()`

## Sintaxis
Las sentencias `if` te permiten ejecutar código solo si una condición es `True`. Son como un bucle `while` que no se repite.
El `if` toma una condición al igual que el bucle `while` y ejecuta el bloque de código del if si la condición se evalúa como `True`:

`#haz un flip si la condición es verdadera
if condition:
	do_a_flip()`

También puedes agregar un `else` después del if que define el código a ejecutar si la condición es `False`:

`if condition:
	#haz un flip si la condición es verdadera
	do_a_flip()
else:
	#de lo contrario, cosecha
	harvest()`

`elif` es una abreviatura de else if.

`if condition1:
	#a
else:
	if condition2:
		#b
	else:
		#c`

puede ser abreviado a:

`if condition1:
	#a
elif condition2:
	#b
else:
	#c`
