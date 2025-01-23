# Fertilizer
En algún momento, esperar simplemente a que las plantas crezcan ya no es suficiente.
Al igual que el agua, recibes automáticamente 1 fertilizante cada 10 segundos, más uno adicional por cada mejora.

El fertilizante hace que las plantas crezcan instantáneamente. `use_item(Items.Fertilizer)` reduce el tiempo de crecimiento restante de la planta bajo el dron en 2 segundos.

Esto tiene algunos efectos secundarios.
Las plantas que han crecido con fertilizante quedarán infectadas.

Cuando una planta está infectada, la mitad de su producción se convierte en `Items.Weird_Substance` al ser cosechada.
Weird Substance también se puede usar en plantas, lo que hace que se active o desactive el estado de infección en la planta y en todas las plantas adyacentes.

Entonces, si llamas a `use_item(Items.Weird_Substance)` en una planta infectada, la curarás, pero si la usas en una planta saludable, la infectarás.

Si lo usas en una planta infectada que tiene vecinas sanas, se curará esa planta pero infectarás a las vecinas, y viceversa.
