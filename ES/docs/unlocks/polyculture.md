# Polyculture
La hierba, los arbustos, los árboles y las zanahorias rinden diez veces más cuando tienen la planta compañera adecuada. La preferencia de compañero es diferente para cada planta individual y no se puede predecir. Afortunadamente, la preferencia de compañero de la planta bajo el dron se puede medir usando `get_companion()`. Devuelve una lista donde el primer elemento es el tipo de planta que quiere como compañera y el segundo y tercer elementos son las coordenadas x e y de la posición donde quiere a su compañera.

Por ejemplo, si plantas un arbusto y luego llamas a `get_companion()`, devolverá algo como `[Entities.Carrots, 3, 5]`. Esto significa que este arbusto quisiera tener zanahorias en la posición `(3,5)`. Así que si plantas zanahorias en `(3,5)` y luego cosechas el arbusto, rendirá diez veces más madera. La etapa de crecimiento de la zanahoria no importa.

La preferencia de compañero de una planta puede ser `Entities.Grass`, `Entities.Bush`, `Entities.Tree` o `Entities.Carrots`. Cada planta elige esto al azar, pero siempre elegirá una planta diferente a sí misma. La posición también puede ser cualquier posición dentro de 3 movimientos de la planta, excepto la posición de la propia planta.

Si no hay una planta bajo el dron que tenga una preferencia de compañero, `get_companion()` devolverá `None`.
