# Expansion 1

Votre ferme s'est agrandie ! Cet espace n'est pas très utile si vous ne pouvez pas déplacer le drone, donc il y a une nouvelle fonction `move()` qui déplace le drone. `move()` nécessite que vous spécifiiez la direction dans laquelle vous souhaitez déplacer le drone. Il y a quatre nouvelles constantes pour cela : `North, East, South, West`

Par exemple, `move(North)` déplacera le drone d'une case vers le nord.

Si vous dépassez le bord de la ferme, le drone sera déplacé de l'autre côté de la ferme. Le code d'exemple suivant continuera à se déplacer vers le nord et reviendra au début lorsqu'il atteindra le bord de la ferme :

`while True:
    move(North)`