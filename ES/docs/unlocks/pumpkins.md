# Calabazas
[Pumpkins](objects/pumpkin) crecen como zanahorias en tierra cultivada. Plantarlas cuesta zanahorias.

Cuando todas las calabazas en un cuadrado están completamente maduras, crecerán juntas para formar una calabaza gigante. Desafortunadamente, las calabazas tienen un 20% de probabilidad de morir una vez maduras, por lo que necesitarás replantar las muertas si deseas que se fusionen.

El rendimiento de una calabaza gigante depende de su tamaño.

Una calabaza de 1x1 produce `1*1*1 = 1` calabaza.
Una calabaza de 2x2 produce `2*2*2 = 8` calabazas en lugar de `4`.
Una calabaza de 3x3 produce `3*3*3 = 27` calabazas en lugar de `9`.
Una calabaza de 4x4 produce `4*4*4 = 64` calabazas en lugar de `16`.
Una calabaza de `n`x`n` produce `n*n*5` calabazas para `n >= 5`.

Es buena idea obtener calabazas de al menos 5x5 para aprovechar la bonificación completa.

Esto significa que incluso si plantas una calabaza en cada baldosa de un cuadrado, puede que una muera e impida que crezca la mega calabaza.
