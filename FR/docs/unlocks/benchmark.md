# Benchmark

Il existe deux fonctions utiles pour mesurer la durée des opérations :

`get_time()` retourne le temps en secondes depuis le début du jeu.

`get_op_count()` retourne le nombre d'opérations effectuées depuis le début de l'exécution.

La plupart des actions nécessitent un nombre constant d'opérations, et tant que le facteur de vitesse reste le même, le temps par opération est également constant.

Les actions qui n'affectent pas le drone, telles que la lecture de variables et l'appel de fonctions, comptent toutes comme `1` opération. (Appeler une fonction consiste généralement à lire la fonction à partir d'une variable puis à l'appeler, donc cela fait `2` opérations)

Les actions du drone comme planter, récolter ou se déplacer comptent comme `200` opérations.

Notez que la performance dans le monde réel est beaucoup plus complexe que cela. Des comptes d'opérations constants comme ceux-ci sont une simplification faite pour ce jeu.