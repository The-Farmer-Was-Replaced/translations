# Watering
Las plantas crecen más rápido cuando se riegan. El suelo tiene un nivel de agua que varía de `0` a `1`.
La función `get_water()` devuelve el nivel de agua del suelo sobre el que se encuentra.

La velocidad de crecimiento de una planta que crece en suelo labrado aumenta linealmente desde una velocidad de 1x a nivel de agua 0 hasta una velocidad de 5x a nivel de agua 1.
El riego solo afecta a las plantas que crecen en suelo labrado. No tiene ningún efecto en las plantas que crecen en césped.

El suelo se seca con el tiempo: el agua pierde el 1% de su nivel actual cada cierto tiempo. Mantener el nivel de agua alto consumirá mucho más agua que mantenerlo bajo.

Puedes usar tanques de agua para regar tus plantas. Puedes comprar tanques vacíos con madera usando `trade(Items.Empty_Tank)`.

Un tanque puede contener `0.25` de agua.

Los tanques se llenan automáticamente. La tasa de llenado es del `0.5`% del número de tanques vacíos por segundo. Así que si tienes `100` tanques vacíos, uno de ellos se llenará cada `2` segundos.

Llama a `use_item(Items.Water_Tank)` sobre cualquier suelo para vaciar un tanque y regar el suelo.
