# Expand 1
¡Tu granja ha crecido! East espacio no es de mucha utilidad si no puedes mover el dron, así que hay una nueva función `move()` que mueve el dron. `move()` requiere que especifiques la dirección en la que quieres mover el dron. Hay cuatro nuevas constantes para esto: `North, East, South, West`.

Por ejemplo, `move(North)` moverá el dron un cuadro hacia el norte.

Si te mueves más allá del borde de la granja, el dron se moverá al otro lado de la granja.
El siguiente código de ejemplo seguirá moviéndose hacia el norte y volverá al inicio cuando llegue al borde de la granja:

`while True:
	move(North)`
