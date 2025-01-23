# Continue
`continue` позволяет завершить текущую итерацию цикла и перейти к следующей итерации самого внутреннего цикла.

`for i in range(10):
	continue
    print("это никогда не печатается")`

Этот код выполняет все `10` итераций цикла, но оператор `print` после `continue` всегда пропускается.

continue также работает в циклах `while`.

`while True:
	if not can_harvest():
		continue
    
    harvest()`

Этот код вызывает `harvest()` только тогда, когда `can_harvest()` возвращает `True`. 
Это эквивалентно:

`while True:
	if can_harvest():
		harvest()`

Вложенные циклы: `continue` всегда влияет на самый внутренний цикл.

`for i in range(10):
	for j in range(10):
	    print("это печатается 100 раз")
		continue
		print("это никогда не печатается")
	print("это печатается 10 раз")`