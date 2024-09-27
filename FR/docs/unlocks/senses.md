# Sens

Le drone peut voir maintenant !

Les fonctions `get_pos_x()` et `get_pos_y()` renvoient la position actuelle x et y du drone. À la position de départ, elles sont toutes deux `0`. La position x augmente de `1` à chaque case vers l'`Est` et la position y augmente de `1` à chaque case vers le `Nord`.

`num_items(item)` renvoie combien d'un article vous avez.
Par exemple, `num_items(Items.Hay)` renvoie combien de foin vous avez.

`get_entity_type()` et `get_ground_type()` renvoient le type d'entité ou de sol qui est sous le drone. Une fois que vous avez débloqué les Opérateurs, vous pouvez vérifier si le drone est au-dessus d'une entité ou d'un sol spécifique :

Faites une pirouette si vous êtes au-dessus d'un buisson :
`if get_entity_type() == Entities.Bush:
	do_a_flip()`

Le mot-clé `None` est également débloqué maintenant ! `None` est une valeur qui représente qu'il n'y a pas de valeur.
Par exemple, une fonction qui n'a pas d'instruction `return` renverra en fait `None`.

`get_entity_type()` renvoie `None` s'il n'y a pas d'entité sous le drone.