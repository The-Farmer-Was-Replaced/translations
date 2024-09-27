# Senses
¡El dron puede ver ahora!

Las funciones `get_pos_x()` y `get_pos_y()` devuelven la posición actual x e y del dron. En la posición inicial, ambas son `0`. La posición x aumenta en `1` cada casilla hacia el `East` y la posición y aumenta en `1` cada casilla hacia el `North`.

`num_items(item)` devuelve cuántos de un artículo tienes.
Por ejemplo, `num_items(Items.Hay)` devuelve cuánta paja tienes.

`get_entity_type()` y `get_ground_type()` devuelven el tipo de entidad o suelo que está debajo del dron. Una vez que hayas desbloqueado Operadores, puedes verificar si el dron está sobre una entidad o suelo específico:

Haz una voltereta si estás sobre un arbusto:
`if get_entity_type() == Entities.Bush:
	do_a_flip()`

¡La palabra clave `None` también está desbloqueada ahora! `None` es un valor que representa que no hay valor.
Por ejemplo, una función que no tiene una declaración `return` en realidad devolverá `None`.

`get_entity_type()` devuelve `None` si no hay ninguna entidad debajo del dron.
