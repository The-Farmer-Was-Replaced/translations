# Wenn
Du kannst `if`, `elif` und `else` verwenden, um Code bedingt auszuführen.

`if condition1:
	do_a_flip()
elif condition2:
	harvest()
else:
	do_a_flip()
	harvest()`

## Syntax
`if`-Anweisungen ermöglichen es dir, Code nur auszuführen, wenn eine Bedingung `True` ist. Sie sind wie eine `while`-Schleife, die jedoch nicht wiederholt wird.
Das `if` nimmt eine Bedingung wie die `while`-Schleife und führt den if-Codeblock aus, wenn die Bedingung `True` ergibt:

`#Führe einen Flip aus, wenn die Bedingung wahr ist
if condition:
	do_a_flip()`

Du kannst auch ein `else` nach dem if hinzufügen, das definierten Code ausführt, wenn die Bedingung `False` ist:

`if condition:
	#führe einen Flip aus, wenn die Bedingung wahr ist
	do_a_flip()
else:
	#ansonsten ernten
	harvest()`

`elif` ist kurz für else if.

`if condition1:
	#a
else:
	if condition2:
		#b
	else:
		#c`

kann verkürzt werden zu:

`if condition1:
	#a
elif condition2:
	#b
else:
	#c`
