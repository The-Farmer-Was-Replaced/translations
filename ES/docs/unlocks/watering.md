# Riego
Las plantas crecen más rápido cuando están regadas. El suelo tiene un nivel de agua que va de `0` a `1`.
La función `get_water()` devuelve el nivel de agua del suelo sobre el que se encuentra.

La velocidad de crecimiento de una planta aumenta linealmente desde 1x de velocidad con nivel de agua 0 hasta 5x de velocidad con nivel de agua 1.

El suelo se seca con el tiempo: Pierde el 1% de su agua actual aproximadamente cada segundo. Mantener un nivel alto de agua consumirá mucha más agua que mantener un nivel bajo.

Puedes usar tanques de agua para regar tus plantas. Se añade automáticamente un tanque de agua a tu inventario cada 10 segundos.
Mejorar `Unlocks.Watering` te dará un tanque de agua adicional cada 10 segundos.

Un tanque puede contener `0.25` de agua.

Llama a `use_item(Items.Water)` sobre cualquier suelo para regarlo.
