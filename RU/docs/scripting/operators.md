# Operators
арифметические операторы: `+, -, *, /, //, %, **`
операторы сравнения: `==, !=, <=, >=, <, >`
логические операторы: `not, and, or`

Примечание: Все числа в игре являются числами с плавающей запятой. Поэтому все арифметические операторы являются операторами с плавающей запятой.
`//` определен как оператор, который просто округляет число вниз после деления.

Для операторов присваивания вам нужно разблокировать "Переменные".

## Введение
Операторы позволяют сравнивать, изменять и комбинировать значения.
Арифметические операторы `+, -, *, /, //, %, **` используются для выполнения обычных математических операций с числами.
Операторы сравнения `==, !=, <=, >=, <, >` используются для сравнения значений. Результат всегда либо `True`, либо `False`.
Логические операторы (также называемые булевыми операторами) `not, and, or` используются для комбинирования логических значений.

## Арифметические операторы
`+` и `-` используются для сложения и вычитания.

`2 + 3` оценивается как `5`
`3 - 2` оценивается как `1`

`*`, `/` и `//` используются для умножения и деления.

`2 * 3` оценивается как `6`
`5 / 2` оценивается как `2.5`

`//` делает то же самое, что и `/`, но результат округляется вниз (до ближайшего целого числа).

`5 // 2` оценивается как `2`

`%` является оператором модуля, также известным как оператор остатка. Он по сути делит два числа и затем возвращает остаток. Вы также можете думать о нем как о повторном вычитании правого числа из левого числа до тех пор, пока остаток не станет меньше правого числа.

`4 % 2` оценивается как `0`
`5 % 2` оценивается как `1`
`6 % 2` оценивается как `0`
`2 % 6` оценивается как `2`
`1.5 % 1` оценивается как `0.5`

`**` является оператором возведения в степень.

`2**2` оценивается как `4`
`(-5)**3` оценивается как `-125`

## Операторы сравнения
`==` и `!=` используются для проверки, равны ли два значения (`==`) или не равны (`!=`). Они могут использоваться для всех типов значений.

`2 == 2` оценивается как `True`
`Entities.Bush != Entities.Bush` оценивается как `False`
`3 != 3 + 1` оценивается как `True`

`<=, >=, <, >` могут использоваться только для чисел. Они проверяют, является ли левое число "меньше или равно" (`<=`), "больше или равно" (`>=`), "меньше" (`<`) или "больше" (`>`) правого числа.

`1 <= 1` оценивается как `True`
`2 >= 3` оценивается как `False`
`-2 < -1` оценивается как `True`
`6 > 6` оценивается как `False`

## Логические операторы
`not` просто инвертирует значение:

`not False` оценивается как `True`
`not True` оценивается как `False`

`and` оценивается как `True` только если оба значения `True`

`True and True` оценивается как `True`
`True and False` оценивается как `False`
`False and False` оценивается как `False`

`or` оценивается как `True`, если хотя бы одно из значений `True`

`True or True` оценивается как `True`
`True or False` оценивается как `True`
`False or False` оценивается как `False`
