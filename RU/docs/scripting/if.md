# If
Вы можете использовать `if`, `elif` и `else` для выполнения кода по условию.

`if condition1:
	do_a_flip()
elif condition2:
	harvest()
else:
	do_a_flip()
	harvest()`

## Синтаксис
`if` позволяет выполнять код только если условие равно `True`. Это похоже на цикл `while`, но без повторения. 
`if` принимает условие так же, как цикл `while`, и выполняет блок кода, если условие равно `True`:

`#сделать переворот, если условие True
if condition:
	do_a_flip()`

Вы также можете добавить `else` после `if`, чтобы определить код, который будет выполняться, если условие равно `False`:

`if condition:
	#сделать переворот, если условие True
	do_a_flip()
else:
	#иначе собрать урожай
	harvest()`

`elif` это сокращение от "else if".

`if condition1:
	#a
else:
	if condition2:
		#b
	else:
		#c`

можно сократить до:

`if condition1:
	#a
elif condition2:
	#b
else:
	#c`
