# Цикл For
Цикл `for` работает так же, как в Python (в некоторых языках называется foreach, не путать с циклом C-стиля, который отличается).

`for i in sequence:
	#сделать что-то с i`

Как и цикл `while`, `for` многократно выполняет блок кода. Однако вместо выполнения на основе условия, он выполняет тело цикла один раз для каждого элемента в последовательности.

## Синтаксис
Цикл `for` выглядит так:

`for variable_name in sequence:
	#блок кода`

`variable_name` это любое имя, которое вы выберете. Это переменная, которая хранит текущий элемент последовательности. `sequence` должна быть значением, которое можно итерировать, например, диапазоном или числами. Блок кода выполняется для каждого элемента, с присваиванием текущего элемента переменной цикла.

## Последовательности
[Диапазоны](functions/range)      <unlock=lists>[Списки](docs/scripting/lists.md)      </unlock><unlock=functions>[Кортежи](docs/scripting/tuples.md)      </unlock><unlock=dicts>[Словари](docs/scripting/dicts.md)      </unlock><unlock=sets>[Множества](docs/scripting/sets.md)</unlock>

## Пример
`for i in range(5):
    harvest()`

Этот цикл выполняет тело фиксированное количество раз. По сути, это то же самое, что написать

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

Поэтому он вызывает `harvest()` 5 раз.

Смотрите также [Break](docs/scripting/break) и [Continue](docs/scripting/continue)