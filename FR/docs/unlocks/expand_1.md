# Étendre 1
<unlock=for>Voir aussi [Expand_2](docs/unlocks/expand_2.md)

</unlock>Votre ferme s’est agrandie ! Cet espace ne sert pas à grand-chose si vous ne pouvez pas déplacer le drone, donc il y a une nouvelle fonction `move()` qui déplace le drone. `move()` exige que vous précisiez la direction dans laquelle vous souhaitez déplacer le drone. Quatre constantes sont disponibles pour cela : `North, East, South, West`.

Par exemple, `move(North)` déplacera le drone d’une case vers le nord.

Si vous sortez des limites de la ferme, le drone réapparaîtra de l’autre côté.
Le code d’exemple suivant va se déplacer indéfiniment vers le nord et revenir au début quand il atteint le bord :

`while True:
	move(North)`
