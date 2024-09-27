# If
Puedes usar if, elif y else para ejecutar código condicionalmente.

`if condition1:
	haz_un_flip()
elif condition2:
	cosecha()
else:
	haz_un_flip()
	cosecha()`

## Sintaxis
`if` te permite ejecutar código solo si alguna condición es `True`. Son como un bucle `while` que no se repite.
El `if` toma una condición al igual que el bucle `while` y ejecuta el bloque de código if si la condición se evalúa como `True`:

`#haz un flip si la condición es True
if condition:
	haz_un_flip()`

También puedes agregar un `else` después del if que define el código a ejecutar si la condición se evalúa como `False`:

`if condition:
	#haz un flip si la condición es True
	haz_un_flip()
else:
	#de lo contrario, cosecha
	cosecha()`

`elif` es la abreviatura de else if.

`if condition1:
	#a
else:
	if condition2:
		#b
	else:
		#c`

se puede acortar a:

`if condition1:
	#a
elif condition2:
	#b
else:
	#c`
