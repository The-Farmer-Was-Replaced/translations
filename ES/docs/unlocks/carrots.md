# Carrots
Antes de que puedas plantar zanahorias con `plant(Entities.Carrots)`, tienes que hacer dos cosas nuevas. Primero, las zanahorias solo pueden crecer en suelo labrado. Para labrar el suelo, simplemente llama a `till()`. Llamar a `till()` nuevamente lo cambiará de nuevo a `Grounds.Turf`.

La segunda nueva característica es que las zanahorias necesitan semillas para crecer. Puedes comprar semillas de zanahoria con la nueva función `trade()`.
Tienes que pasar un tipo de artículo a `trade()` de esta manera: `trade(Items.Carrot_Seed)`

Si el artículo se puede comprar, entonces se comprará con esto.

Puedes ver el costo de cualquier artículo en su tooltip. El tooltip aparece cuando pasas el ratón sobre el artículo en sí o el nombre del artículo en el código.
