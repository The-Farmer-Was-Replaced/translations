# Expandir 1
<unlock=for>También consulta [Expand_2](docs/unlocks/expand_2.md)

</unlock>¡Tu granja ha crecido! Este espacio no sirve de mucho si no puedes mover el dron, por lo que hay una nueva función `move()` que desplaza el dron. `move()` requiere que especifiques la dirección en la que deseas mover el dron. Hay cuatro constantes nuevas para esto: `North, East, South, West`.

Por ejemplo, `move(North)` moverá el dron una casilla hacia el norte.

Si te mueves fuera del límite de la granja, el dron aparecerá en el lado opuesto.
El siguiente ejemplo de código se moverá infinitamente hacia el norte y volverá al inicio cuando alcance el borde:

`while True:
	move(North)`
