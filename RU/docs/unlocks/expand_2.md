# Expand 2
Ваша ферма снова расширилась! Теперь плитки больше не находятся в одном ряду, поэтому вам нужно найти способ перемещаться по квадратной сетке.

С циклом `while` это невозможно, пока вы не разблокируете чувства и операторы.
Пора познакомиться с циклом `for`.

Вы можете прочитать все о цикле `for` на странице [For Loop](docs/scripting/for), но сейчас вам понадобится только повторять код фиксированное количество раз.

`#выполнить n переворотов
for i in range(5):
	do_a_flip()`

`range(n)` создает диапазон чисел от `0` до `n-1`, который содержит `n` элементов. Цикл `for` выполняет тело цикла один раз для каждого элемента в последовательности. В этом примере `do_a_flip()` будет вызвано `5` раз.

Функция `get_world_size()` также доступна сейчас. Она возвращает длину стороны вашей фермы. Таким образом, вы можете написать код, который не сломается при следующем обновлении расширения.

`for i in range(get_world_size()):
	harvest()
	move(North)`

Этот пример собирает урожай в одном столбце фермы для любого размера фермы.

Если вы застряли, пытаясь понять, как перемещать дрон по ферме, посмотрите подсказку ниже.
<spoiler=показать подсказку> Конечно, есть несколько способов перемещаться по ферме.
Мы ищем способ систематически обходить ферму, который не сломается, когда ферма снова вырастет.
Систематический способ добраться до каждого места на ферме — повторять следующие 2 шага бесконечно:

1. Двигайтесь на `Север`, пока не вернетесь обратно.
2. Двигайтесь на `Восток`

`for i in range(get_world_size()):` может быть полезен для превращения этой идеи в код.
</spoiler>
<spoiler=показать возможное решение> Базовый обход может выглядеть так:

`for i in range(get_world_size()):
	for j in range(get_world_size()):
		#выполнить переворот на каждой плитке
		do_a_flip()
		move(North)
	move(East)`
</spoiler>
