# Laberintos
`Items.Weird_Substance`, que se obtiene al [fertilizing](docs/unlocks/fertilizer.md) plantas, tiene un efecto extraño en los arbustos. Si el dron está sobre un arbusto y llamas a `use_item(Items.Weird_Substance, amount)`, el arbusto crecerá hasta convertirse en un laberinto de setos.
El tamaño del laberinto depende de la cantidad de `Items.Weird_Substance` usada (el segundo argumento de la llamada a `use_item()`).
Sin mejoras de laberinto, usar `n` `Items.Weird_Substance` creará un laberinto de `n`x`n`. Por cada nivel de mejora de laberinto necesitas usar `n` `Items.Weird_Substance` adicionales para obtener el mismo efecto.
Así que para crear un laberinto que ocupe todo el campo:

`plant(Entities.Bush)
n_substance = get_world_size() * num_unlocked(Unlocks.Mazes)
use_item(Items.Weird_Substance, n_substance)`

Por alguna razón el dron no puede volar sobre los setos, a pesar de que no parecen tan altos.

Hay un tesoro escondido en alguna parte del seto. Usa `harvest()` en el tesoro para recibir oro equivalente al área del laberinto. (Por ejemplo, un laberinto de 5x5 proporcionará 25 de oro.)

Si usas `harvest()` en cualquier otro lugar, el laberinto simplemente desaparecerá.

`get_entity_type()` es igual a `Entities.Treasure` si el dron está sobre el tesoro y `Entities.Hedge` en cualquier otro lugar del laberinto.

Los laberintos no contienen bucles a menos que reutilices el laberinto (ver abajo cómo reutilizar un laberinto). Por lo tanto, no hay forma de regresar a la misma posición sin retroceder.

Puedes comprobar si hay una pared intentando atravesarla.
`move()` devuelve `True` si lo logra y `False` de lo contrario.

Si no tienes idea de cómo llegar al tesoro, revisa la pista 1. Muestra cómo abordar un problema de este tipo.

Para un desafío adicional, puedes reutilizar el laberinto usando la misma cantidad de `Items.Weird_Substance` sobre el tesoro nuevamente.
Esto aumentará la cantidad de oro en el tesoro en un laberinto completo y lo moverá a una posición aleatoria en el laberinto.

Si usas `measure()` sobre un tesoro, obtendrás la posición a la que se moverá, como una tupla:
`next_x, next_y = measure()`

Cada vez que el tesoro se mueve, es posible que se elimine una pared aleatoria del laberinto. De este modo, los laberintos reutilizados pueden contener bucles.

Ten en cuenta que los bucles en el laberinto lo complican mucho más, porque significa que puedes llegar a la misma ubicación sin retroceder.
Reutilizar un laberinto no te da más oro que simplemente cosecharlo y crear uno nuevo.
Es 100% un desafío adicional que puedes omitir si lo deseas.
Solo vale la pena si la información adicional y los atajos te ayudan a resolver el laberinto más rápido.

El mismo laberinto puede resolverse un máximo de 300 veces. Esto corresponde a 299 reubicaciones. Después de eso, usar weird substance en el tesoro ya no tendrá efecto.

<spoiler=show hint 1>Este es un enfoque general para resolver el problema:

Crea un laberinto e imagina que eres el dron.

Piensa en cómo tratarías de encontrar el tesoro si estuvieras dentro del laberinto.

Escribe tu estrategia paso a paso para que otra persona pueda seguirla sin pensar.

Ahora intenta traducir esos pasos en código.
</spoiler>
<spoiler=show hint 2>Mientras no haya bucles: Todas las paredes forman básicamente una sola pared conectada. Si sigues esa pared, te guiará a través de todo el laberinto.
Este método requiere muy poco código y no necesitas llevar registro de dónde has estado. Unas 10 líneas de código son suficientes.</spoiler>
<spoiler=show hint 3>En lugar de moverte con direcciones absolutas, como `East` o `West`, puede ser muy útil moverte con direcciones relativas como "girar a la derecha" o "girar a la izquierda". Para ello, debes rastrear hacia dónde se está moviendo actualmente el dron. El dron nunca gira en realidad, pero aún puedes llevar una "rotación virtual" en el código.
Este truco de índice puede ayudar:

`directions = [North, East, South, West]
index = 0`

Usa `% 4` para rotar "alrededor del reloj", de modo que después de `West` vuelva a `North`:
`# turn right
index = (index + 1) % 4`

`# turn left
index = (index - 1) % 4

move(directions[index])`
</spoiler>
<spoiler=show hint 4>Si no puedes resolverlo, siempre puedes hacerlo de forma menos eficiente.
Resolver un laberinto de `1`x`1` es trivial.
</spoiler>
