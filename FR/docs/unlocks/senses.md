# Sens
Le drone peut maintenant voir !

Les fonctions `get_pos_x()` et `get_pos_y()` renvoient la position x et y actuelle du drone. À la position de départ, elles sont toutes les deux à `0`. La position x augmente de `1` pour chaque case vers l'`East` et la position y augmente de `1` pour chaque case vers le `North`.

`num_items(item)` renvoie combien d'un objet vous possédez.
Par exemple, `num_items(Items.Hay)` renvoie combien de foin vous avez.

`get_entity_type()` et `get_ground_type()` renvoient le type d'entité ou de sol qui se trouve sous le drone.

Faire un flip si vous êtes au-dessus d'un buisson :
`if get_entity_type() == Entities.Bush:
    do_a_flip()`

Le mot-clé `None` est également débloqué maintenant ! `None` est une valeur qui représente l'absence de valeur.
Par exemple, une fonction qui n'a pas d'instruction `return` renverra en fait `None`.

`get_entity_type()` renvoie `None` s'il n'y a pas d'entité sous le drone.
