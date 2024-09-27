# Cactus
Los cactus pueden cultivarse en el suelo a partir de semillas de cactus.

Tienen un extraño sentido de comunidad.

Cuando cosechas un cactus, todos los cactus en el campo son cosechados.
El número de elementos de cactus que se obtienen por cactus es igual al tamaño del mundo, tal como lo devuelve `get_world_size()`.

Un cactus solo deja caer elementos de cactus cuando se cosecha si está en orden.
Se considera que un cactus está en orden si hay un cactus más pequeño o igual al `South` y al `West` y un cactus más grande o igual al `North` y al `East`.
Esencialmente, los cactus deben estar ordenados en direcciones crecientes de x e y para que dejen caer algo.

Si un cactus está en el borde del campo, solo los campos vecinos existentes necesitan estar correctos para que esté ordenado.

El tamaño de un cactus se puede medir con `measure()`.
Siempre es uno de estos números: `0,1,2,3,4,5,6,7,8,9`.

También puedes pasar una dirección a `measure(dir)` para medir el tile vecino en esa dirección del dron.

Puedes intercambiar un cactus con su vecino en cualquier dirección usando el comando `swap()`.
`swap(direction)` intercambia el objeto bajo el dron con el objeto a un tile en la `dirección` del dron.

<spoiler=mostrar pista 1>
Si cada columna y cada fila del campo están ordenadas, entonces todas las plantas están en orden.
</spoiler>
<spoiler=mostrar pista 1>
Recibes una recompensa por cada cactus que esté en orden. Si algunos cactus están en orden, ya recibirás parte de la recompensa. No tienes que ordenar el 100%.</spoiler>
