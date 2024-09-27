# For Loop
Цикл `for` работает так же, как в Python. (Называется циклом foreach в некоторых языках, не путать с циклом for в стиле C, который является другой конструкцией).

`for i in sequence:
	#do something with i`

Подобно циклу `while`, цикл `for` также многократно вызывает блок кода. Вместо выполнения цикла на основе условия, он выполняет тело цикла один раз для каждого элемента в последовательности.

## Синтаксис
Цикл for выглядит следующим образом:

`for variable_name in sequence:
	#code block`

`variable_name` может быть любым именем, которое вы выберете. Это переменная, которая хранит текущий элемент в последовательности. `sequence` должна быть значением, которое можно итерировать, например, диапазоном или числами. Блок кода выполняется для каждого элемента с присвоением переменной цикла этому элементу.

## Последовательности
[Диапазоны](functions/range)      <unlock=lists>[Списки](docs/scripting/lists.md)      </unlock><unlock=functions>[Кортежи](docs/scripting/tuples.md)      </unlock><unlock=dicts>[Словари](docs/scripting/dicts.md)      </unlock><unlock=sets>[Множества](docs/scripting/sets.md)</unlock>

## Пример
`for i in range(5):
	harvest()`

Этот цикл выполняет тело фиксированное количество раз. Это по сути то же самое, что и написание

`i = 0
harvest()
i = 1
harvest()
i = 2
harvest()
i = 3
harvest()
i = 4
harvest()`

Таким образом, он вызывает `harvest()` 5 раз.

См. также [Break](docs/scripting/break) и [Continue](docs/scripting/continue)
