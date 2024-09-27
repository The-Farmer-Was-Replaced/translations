# Functions
Usa la palabra clave `def` para definir una nueva función:
`def f(arg1, arg2 = False):
	#código de la función`

Puedes usar el operador de llamada `()` para llamar a la función:
`f(42)`

A diferencia de Python, las funciones definidas en el ámbito global de cualquier archivo abierto pueden ser llamadas por su nombre, incluso si la declaración `def` nunca ha sido ejecutada.
Consulta [Ámbitos](docs/scripting/scopes.md) para más información sobre esto.

## Introducción
Ya has visto funciones integradas como `harvest()`.
También puedes definir tus propias funciones, lo que permite estructurar tu código de una manera modular. Básicamente, te permite dar un nombre a un bloque de código para que puedas llamarlo desde cualquier lugar que desees.

## Definiciones de Funciones
Por ejemplo, podrías definir una función que mueva el dron varias veces.

`def move_n_dir(n, dir):
	for i in range(n):
		move(dir)`

La palabra clave `def` indica que esta es una definición de función.
`move_n_dir` es el nombre al que se vincula la función. East puede ser cualquier nombre de variable válido y se usará para llamar a la función.
`n` y `dir` son parámetros. Son variables que contienen los valores que se pasan a la función (Estos valores también se llaman argumentos). Puedes agregar tantos parámetros a una definición de función como desees.
Después de los `:` viene el bloque de código que se ejecutará cuando se llame a la función.

Con la definición anterior, el siguiente código mueve el dron `10` casillas al `North` y `2` casillas al `West`.

`move_n_dir(10, North)
move_n_dir(2, West)`

## Valores de Retorno
Usa la palabra clave `return` para hacer que una función devuelva un valor.
Por ejemplo, la siguiente función define la operación de exclusión o. La exclusión o devuelve `True` si un valor es `True` y el otro es `False`:

`def xor(a, b):
	return a != b

if xor(True, False):
	do_a_flip()`

[Tuplas](docs/scripting/tuples.md) permiten devolver múltiples valores.

## Argumentos por Defecto
También puedes asignar valores por defecto que se usarán si no se pasan argumentos.

`def f(a = False):
	if a:
		do_a_flip()

f()

f(True)`

Un argumento que tiene un valor por defecto no puede ser seguido por un argumento que no tenga un valor por defecto.

## Uso Avanzado de Funciones
Las funciones son valores como cualquier otro valor, y la declaración `def` actúa como una declaración de asignación, asignando la función al nombre que le des.
Esto permite hacer cosas como esta:

`def f():
	def d():
		do_a_flip()
	return d

f()()`

Aquí `f()` llama a la función `f` que define y devuelve una nueva función `d`. El segundo `()` luego ejecuta la función devuelta y realiza el giro.
(Hacer este tipo de cosas generalmente no es una buena idea porque es difícil ver lo que está pasando)

Las funciones que toman otras funciones como argumentos te permiten ser realmente creativo:

`def f(g, arg):
	for _ in range(10):
		g(arg)

f(move, North)
f(use_item, Items.Fertilizer)`

East código mueve el dron `North` 10 veces y luego usa fertilizante 10 veces.
