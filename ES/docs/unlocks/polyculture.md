# Policultivo
Puede que ya hayas notado que a veces las plantas rinden más cuando se siembran juntas.
La hierba, los arbustos, los árboles y las zanahorias dan más cuando tienen la planta compañera adecuada. La preferencia de compañía es diferente para cada planta individual y no puede predecirse. Afortunadamente, la preferencia de compañía de la planta bajo el dron puede medirse usando `get_companion()`. Devuelve una tupla en la que el primer elemento es el tipo de planta que quiere como compañera y el segundo elemento es la posición donde quiere a su compañera.

`plant, (x, y) = get_companion()`

Por ejemplo, si siembras un arbusto y luego llamas a `get_companion()`, podría devolver algo como `(Entities.Carrot, (3, 5))`. Esto significa que a ese arbusto le gustaría tener zanahorias en la posición `(3,5)`. Si siembras zanahorias en `(3,5)` y luego cosechas el arbusto, producirá más madera. La etapa de crecimiento de la zanahoria no importa.

La preferencia de compañía de una planta puede ser `Entities.Grass`, `Entities.Bush`, `Entities.Tree` o `Entities.Carrot`. Cada planta lo elige al azar, pero siempre elegirá un tipo de planta diferente a sí misma. La posición también puede ser cualquier ubicación dentro de 3 movimientos de la planta, excepto la posición de la propia planta.

Si no hay ninguna planta bajo el dron que tenga una preferencia de compañía, `get_companion()` devolverá `None`.

El multiplicador de rendimiento es `5` más el número de mejoras de policultivo.
