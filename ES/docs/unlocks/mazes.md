# Mazes
Si usas fertilizante en un arbusto completamente crecido, se convertirá en un laberinto de setos con una probabilidad del 10%. Por alguna razón, el dron no puede volar sobre los setos, aunque no parecen tan altos.

Hay un tesoro escondido en algún lugar del seto. Usa `harvest()` en el tesoro para recibir oro igual al área del laberinto. (Por ejemplo, un laberinto de 5x5 dará 25 de oro).

Si usas `harvest()` en cualquier otro lugar, el laberinto simplemente desaparecerá.

`get_entity_type()` es igual a `Entities.Treasure` si el dron está sobre el tesoro y `Entities.Hedge` en cualquier otro lugar del laberinto.

Los laberintos no contienen bucles a menos que reutilices el laberinto (ver abajo cómo reutilizar un laberinto). Así que no hay forma de que el dron termine en la misma posición de nuevo sin retroceder.

Puedes comprobar si hay una pared intentando atravesarla.
`move()` devuelve `True` si tuvo éxito y `False` en caso contrario.

Si no tienes idea de cómo llegar al tesoro, echa un vistazo a la Pista 1. Te muestra cómo abordar un problema como este.

Para un desafío adicional, también puedes reutilizar el laberinto usando fertilizante en el tesoro.
Esto tiene una probabilidad del 10% de aumentar el tesoro en un laberinto completo y moverlo a una posición aleatoria en el laberinto.
Usar `measure()` en un tesoro devuelve la posición a la que se moverá a continuación como una tupla `(x_position, y_position)`.

Por ejemplo, estando sobre el tesoro, el siguiente código te da la posición donde estará el tesoro después de fertilizarlo:
`next_x, next_y = measure()`

Cada vez que el tesoro se reubica, puede eliminarse una pared aleatoria del laberinto. Así que los laberintos reutilizados pueden contener bucles.

Ten en cuenta que los bucles en el laberinto lo hacen mucho más difícil, por lo que si eres principiante, puede que no quieras reutilizar laberintos. Reutilizar laberintos no te da más oro que generar un nuevo laberinto. Solo vale la pena si la información adicional y los atajos te ayudan a resolver el laberinto más rápido.

El mismo laberinto se puede resolver un máximo de 300 veces. Esto corresponde a 299 reubicaciones. Después de eso, fertilizar el tesoro ya no tendrá ningún efecto.

<spoiler=mostrar pista 1>Aquí tienes un enfoque general para resolver el problema:

Crea un laberinto e imagina que eres el dron.

Piensa en cómo intentarías encontrar el tesoro si estuvieras en el laberinto.

Escribe tu estrategia paso a paso para que alguien más pueda seguirla sin pensar.

Ahora intenta traducir tus pasos en código.
</spoiler>
<spoiler=mostrar pista 2>Para laberintos sin ciclos: Todas las paredes son realmente una gran pared conectada. Si sigues la pared, te llevará a través de todo el laberinto.</spoiler>
<spoiler=mostrar pista 3>Puede ser útil llevar un registro de la dirección en la que está mirando el dron para que puedas hacer giros a la izquierda y a la derecha. El dron nunca gira realmente, pero aún puedes mantener una "rotación virtual" en el código.
El siguiente truco de índice podría ser útil para esto:

`directions = [North, East, South, West]
index = 0`

`# girar a la derecha`
`# el % 4 hace que se envuelva
index = (index + 1) % 4`

`# girar a la izquierda
index = (index - 1) % 4

move(directions[index])`</spoiler>
<spoiler=mostrar pista 4>Si no puedes resolverlo, siempre puedes facilitarte la vida y hacerlo de manera menos eficiente.
No tienes que ser capaz de llegar al tesoro cada vez, siempre puedes cosechar y generar un nuevo laberinto.
Incluso hay una pequeña posibilidad de que el tesoro aparezca justo debajo del dron cuando creas un laberinto.</spoiler>
