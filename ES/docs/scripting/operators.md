# Operators
operadores aritméticos: `+, -, *, /, //, %, **`
operadores de comparación: `==, !=, <=, >=, <, >`
operadores booleanos: `not, and, or`

Nota: Todos los números en el juego son números de punto flotante. Por lo tanto, todos los operadores aritméticos son operadores de punto flotante.
`//` está definido para simplemente redondear hacia abajo el número después de la división.

Para los operadores de asignación necesitas desbloquear el "Desbloqueo de Variables".

## Introducción
Los operadores te permiten comparar, modificar y combinar valores.
Los operadores aritméticos `+, -, *, /, //, %, **` se utilizan para realizar operaciones matemáticas comunes en números.
Los operadores de comparación `==, !=, <=, >=, <, >` se utilizan para comparar valores. El resultado siempre es `True` o `False`.
Los operadores lógicos (también llamados operadores booleanos) `not, and, or` se utilizan para combinar valores de verdad.

## Operadores Aritméticos
`+` y `-` se utilizan para la suma y la resta.

`2 + 3` evalúa a `5`
`3 - 2` evalúa a `1`

`*`, `/` y `//` se utilizan para la multiplicación y la división.

`2 * 3` evalúa a `6`
`5 / 2` evalúa a `2.5`

`//` hace lo mismo que `/` pero el resultado se redondea hacia abajo (al siguiente número entero).

`5 // 2` evalúa a `2`

`%` es el operador de módulo, también conocido como el operador de resto. Esencialmente divide los dos números y luego devuelve el resto. También puedes pensar en él como restar repetidamente el número derecho del número izquierdo hasta que el resto sea menor que el número derecho.

`4 % 2` evalúa a `0`
`5 % 2` evalúa a `1`
`6 % 2` evalúa a `0`
`2 % 6` evalúa a `2`
`1.5 % 1` evalúa a `0.5`

`**` es el operador de potencia.

`2**2` evalúa a `4`
`(-5)**3` evalúa a `-125`

## Operadores de Comparación
`==` y `!=` se utilizan para verificar si dos valores son "iguales"(`==`) o "no iguales"(`!=`). Pueden ser utilizados en todos los tipos de valores.

`2 == 2` evalúa a `True`
`Entities.Bush != Entities.Bush` evalúa a `False`
`3 != 3 + 1` evalúa a `True`

`<=, >=, <, >` solo pueden ser utilizados en números. Verifican si el número de la izquierda es "menor o igual"(`<=`), "mayor o igual"(`>=`), "menor" (`<`) o "mayor" (`>`) que el número de la derecha.

`1 <= 1` evalúa a `True`
`2 >= 3` evalúa a `False`
`-2 < -1` evalúa a `True`
`6 > 6` evalúa a `False`

## Operadores Lógicos
`not` simplemente invierte el valor:

`not False` evalúa a `True`
`not True` evalúa a `False`

`and` evalúa a `True` solo si ambos valores son `True`

`True and True` evalúa a `True`
`True and False` evalúa a `False`
`False and False` evalúa a `False`

`or` evalúa a `True` si al menos uno de los valores es `True`

`True or True` evalúa a `True`
`True or False` evalúa a `True`
`False or False` evalúa a `False`
