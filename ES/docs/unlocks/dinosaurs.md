# Dinosaurs
Los dinosaurios son criaturas antiguas y majestuosas que se pueden cultivar para obtener huesos antiguos.

Para obtener dinosaurios, debes intercambiar huevos y usarlos con `use_item(Items.Egg)`.

A los dinosaurios les gusta moverse. De vez en cuando, el dinosaurio se intercambiará con un vecino aleatorio.
East intercambio funciona igual que llamar a `swap(direction)` manualmente, excepto que ocurre aleatoriamente de vez en cuando.

Los dinosaurios se pueden cosechar para obtener huesos usando el comando `harvest()`.
Hay 4 tipos diferentes de dinosaurios.
Cosechar un dinosaurio también cosechará todos los dinosaurios adyacentes del mismo tipo, por lo que se cosechará todo un grupo conectado de dinosaurios a la vez.

El tipo de un dinosaurio se puede medir con `measure()`. Esto devolverá un número único para cada tipo de dinosaurio.

Recuerda que también puedes pasar una dirección a measure para medir una entidad junto al dron.
`measure(North)`, por ejemplo, medirá la entidad al norte del dron.

La cantidad de huesos que obtienes depende del tamaño del grupo de dinosaurios que cosechas. Cosechar grupos de hasta 4 dejará caer huesos iguales al cuadrado del tamaño del grupo. Los grupos de tamaño 4 o más grandes dejarán caer huesos iguales a 4 veces el tamaño del grupo.

Por lo tanto, la cantidad de huesos por dinosaurio aumenta con el tamaño del grupo hasta el tamaño 4, y luego permanece constante.
Para una eficiencia óptima, siempre querrás cosechar grupos de tamaño 4 o más grandes.

Los grupos también se envuelven alrededor del lado de la granja. Así que un dinosaurio en el borde de la granja se considera adyacente a un dinosaurio en el otro lado de la granja.
