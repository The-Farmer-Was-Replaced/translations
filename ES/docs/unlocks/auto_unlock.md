# Desbloqueos Automáticos
Para automatizar completamente el juego, puedes usar la función `unlock()` para desbloquear funciones automáticamente.
Por ejemplo, puedes usar `unlock(Unlocks.Speed)` y `unlock(Unlocks.Expand)` para desbloquear las funciones de velocidad y expansión.

Para determinar el costo de un desbloqueo, simplemente usa la función `get_cost()` como lo harías para una planta o artículo.
Ejemplo:
`get_cost(Unlocks.Loops)`
devuelve `{Items.Hay:5}`

Si deseas saber cuántos desbloqueos de un tipo particular tienes, usa la función `num_unlocked(unlock)`.

Por ejemplo, `num_unlocked(Unlocks.Speed)` retornará la cantidad de mejoras de velocidad que tienes.

`num_unlocked(Unlocks.Senses)` retornará `1` si los sentidos están desbloqueados y `0` si no lo están.

También puedes usar `num_unlocked()` en Items, Entities o Grounds. Esto retornará `1` si está desbloqueado, de lo contrario `0`.

Ten cuidado `num_unlocked(Unlocks.Carrots)` retornará la cantidad de veces que fue desbloqueado/actualizado.
`num_unlocked(Items.Carrot)` solo retornará `0` o `1`. (Lo mismo para otras plantas)
