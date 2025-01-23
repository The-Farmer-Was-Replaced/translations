# Girasoles
Los [girasoles](objects/sunflower) recolectan el poder del sol. Puedes cosechar ese poder.

Plantarlos funciona exactamente igual que plantar zanahorias o calabazas.

Cosechar un girasol maduro produce energía.
Si hay al menos 10 girasoles en la granja y cosechas el que tiene el mayor número de pétalos, ¡obtienes 5 veces más energía!

`measure()` devuelve el número de pétalos del girasol bajo el dron.
Los girasoles tienen al menos `7` y como máximo `15` pétalos.
Se pueden medir incluso antes de que estén completamente desarrollados.

Varios girasoles pueden tener el mismo número de pétalos, por lo que también puede haber varios girasoles con el mayor número de pétalos. En este caso, no importa cuál de ellos coseches.

Mientras tengas energía, el dron funcionará al doble de velocidad.
Consume 1 de energía cada 30 acciones (como movimientos, cosechas, plantaciones...)
Ejecutar otras instrucciones de código también puede usar energía, pero mucho menos que las acciones del dron.

En general, todo lo que se acelera con las mejoras de velocidad también se acelera con la energía.
Todo lo que se acelera con energía también usa energía proporcional al tiempo que tarda en ejecutarse, ignorando las mejoras de velocidad.
