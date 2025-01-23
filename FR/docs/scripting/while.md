# Boucle While
Vous avez débloqué la boucle `while` ainsi que les valeurs `True` et `False`. La boucle `while` continue d'exécuter le corps de la boucle tant que la condition est `True`.

`while condition:
	#loop body`

Ne vous inquiétez pas de créer des boucles infinies. Les délais dans l'exécution empêcheront le programme de se bloquer.

## Pour les Débutants
Peut-être avez-vous déjà essayé de mettre plusieurs appels à `harvest()` d'affilée :

`harvest()
harvest()
harvest()`

Cela vous permet de récolter plusieurs fois en une seule exécution du programme.
Cependant, il serait bien de récolter plus de trois fois, et écrire le même code plusieurs fois est une mauvaise pratique.
La solution est une boucle.
Une boucle vous permet d'exécuter le même code plusieurs fois.

La boucle while prend une condition, qui est une valeur logique pouvant être dans un de deux états : `True` ou `False`.
Une telle valeur est appelée une valeur booléenne.

La boucle exécute ensuite le code à l'intérieur de la boucle jusqu'à ce que la condition soit False.
La boucle while ressemble à ceci :

`while condition:
	#loop body
	#loop body
	#...`

Où vous devez remplacer "condition" par une valeur booléenne et `#loop body` par ce que vous voulez faire dans la boucle.

Il y a deux valeurs booléennes constantes disponibles. Les constantes sont des valeurs qui ne changent jamais pendant le programme.

Pour créer une valeur booléenne constante qui est toujours `True`, vous pouvez simplement écrire `True`. Écrivez `False` comme une valeur booléenne constante qui sera toujours `False`.
Vous pourriez donc soit écrire

`while False:
	do_a_flip()`

soit

`while True:
	do_a_flip()`

Le premier ne fera jamais de flip et le second fera des flips indéfiniment (une boucle infinie).

Normalement, créer une boucle infinie est une mauvaise idée car cela fige le programme, mais dans ce jeu, il y a des délais entre chaque itération de la boucle, ce qui fera que le drone continuera à faire un flip jusqu'à ce que vous l'arrêtiez manuellement en appuyant de nouveau sur le bouton exécuter.

Remarquez comment la ligne après les deux-points est indentée. L'indentation comme celle-ci est utilisée pour séparer les blocs de code.
Appuyez simplement sur Tab pour ajouter une indentation et Shift + Tab (ou Backspace) pour la retirer.

La boucle répétera toutes les instructions indentées après les deux-points.
Les instructions après le bloc indenté seront exécutées après que la boucle a terminé.
