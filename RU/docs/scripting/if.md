# If
Вы можете использовать if, elif и else для условного выполнения кода.

`if condition1:
	do_a_flip()
elif condition2:
	harvest()
else:
	do_a_flip()
	harvest()`

## Синтаксис
`if` позволяет выполнять код только если некоторое условие является `True`. Они похожи на цикл `while`, который не зацикливается.
`if` принимает условие, как и цикл `while`, и выполняет блок кода if, если условие оценивается как `True`:

`#сделать сальто, если условие истинно
if condition:
	do_a_flip()`

Вы также можете добавить `else` после if, который определяет код для выполнения, если условие оценивается как `False`:

`if condition:
	#сделать сальто, если условие истинно
	do_a_flip()
else:
	#иначе собрать урожай
	harvest()`

`elif` это сокращение от else if.

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
