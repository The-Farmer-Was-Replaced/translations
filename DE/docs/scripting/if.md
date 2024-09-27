# If
Du kannst `if`, `elif` und `else` verwenden, um Code bedingt auszuführen.

`if bedingung1:
	mach_einen_salto()
elif bedingung2:
	ernte()
else:
	mach_einen_salto()
	ernte()`

## Syntax
`if` ermöglicht es dir, Code nur dann auszuführen, wenn eine Bedingung `True` ist. Sie sind wie eine `while`-Schleife, die nicht schleift.
Das `if` nimmt eine Bedingung genau wie die `while`-Schleife und führt den `if`-Codeblock aus, wenn die Bedingung als `True` bewertet wird:

`#mach einen Salto, wenn die Bedingung wahr ist
if bedingung:
	mach_einen_salto()`

Du kannst auch ein `else` nach dem `if` hinzufügen, das den Code definiert, der ausgeführt wird, wenn die Bedingung als `False` bewertet wird:

`if bedingung:
	#mach einen Salto, wenn die Bedingung wahr ist
	mach_einen_salto()
else:
	#ansonsten ernte
	ernte()`

`elif` ist die Abkürzung für else if.

`if bedingung1:
	#a
else:
	if bedingung2:
		#b
	else:
		#c`

kann verkürzt werden zu:

`if bedingung1:
	#a
elif bedingung2:
	#b
else:
	#c`

