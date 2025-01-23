# Cactus
Como otras plantas, los [cactus](objects/cactus) pueden cultivarse en suelo y cosecharse como de costumbre.

Sin embargo, vienen en varios tamaños y tienen un extraño sentido del orden.

Si cosechas un cactus completamente crecido y todos los cactus vecinos están en orden ordenado, también se cosecharán todos los cactus vecinos de forma recursiva.

Un cactus se considera que está en orden ordenado si todos los cactus vecinos al `Norte` y `Este` están completamente crecidos y son mayores o iguales que él, y todos los cactus vecinos al `Sur` y `Oeste` están completamente crecidos y son menores o iguales que él.

La cosecha solo se extenderá si todos los cactus adyacentes están completamente crecidos y en orden ordenado.
Esto significa que si un cuadrado de cactus crecidos está ordenado por tamaño y cosechas un cactus, se cosechará todo el cuadrado.

Recibirás cactus igual al número de cactus cosechados al cuadrado. Así que si cosechas `n` cactus simultáneamente, recibirás `n**2` `Items.Cactus`.

El tamaño de un cactus puede medirse con `measure()`.
Siempre es uno de estos números: `0,1,2,3,4,5,6,7,8,9`.

También puedes pasar una dirección a `measure(direction)` para medir la casilla vecina en esa dirección del dron.

Puedes intercambiar un cactus con su vecino en cualquier dirección usando el comando `swap()`.
`swap(direction)` intercambia el objeto bajo el dron con el objeto una casilla en la `dirección` del dron.

<spoiler=mostrar pista 1>
Si cada columna y cada fila del campo están ordenadas, entonces todas las plantas están en orden.
</spoiler>
<spoiler=mostrar pista 1>
Recibes una recompensa por cada cactus que esté en orden. Si algunos cactus están en orden, ya recibirás parte de la recompensa. No tienes que ordenar el 100%.</spoiler>
