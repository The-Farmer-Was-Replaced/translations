# Sunflowers
Los girasoles recolectan el poder del sol. Puedes cosechar ese poder.

Plantarlos funciona exactamente de la misma manera que plantar zanahorias, excepto que tienes que comprar semillas de girasol en lugar de semillas de zanahoria.

Sin embargo, cuando cosechas un girasol, el poder de todos los girasoles en la granja fluye junto al girasol cosechado.
Así, cosechar un girasol produce un poder igual a la raíz cuadrada del número de girasoles en la granja.
Solo uno de los girasoles con más pétalos puede manejar esto.
Si cosechas un girasol que no tiene la mayor cantidad de pétalos de todos los girasoles en la granja, el poder destruirá todos los girasoles en la granja.

`measure()` devuelve el número de pétalos del girasol bajo el dron.
Los girasoles tienen al menos `7` y como máximo `15` pétalos.
Pueden ser medidos antes de estar completamente crecidos.

Varios girasoles pueden tener el mismo número de pétalos, por lo que también puede haber varios girasoles con el mayor número de pétalos. En este caso, no importa cuál de ellos coseches.

Mientras tengas poder, el dron lo usará para funcionar el doble de rápido.
Consume 1 poder cada 30 acciones (como moverse, cosechar, plantar...)
Ejecutar otras declaraciones de código también puede usar poder, pero mucho menos que las acciones del dron.

En general, todo lo que se acelera con las mejoras de velocidad también se acelera con el poder.
Cualquier cosa acelerada por el poder también usa poder proporcional al tiempo que tarda en ejecutarse, ignorando las mejoras de velocidad.
