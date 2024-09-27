# Boucle While
Vous avez débloqué la boucle `while` et les valeurs `True` et `False`. La boucle `while` continue d'exécuter le corps de la boucle tant que la condition est `True`.

`while condition:
	#corps de la boucle`

Ne vous inquiétez pas de créer des boucles infinies. Les délais dans l'exécution empêcheront le programme de se figer.

## Pour les Débutants
Peut-être avez-vous déjà essayé de mettre plusieurs appels `harvest()` à la suite :

`harvest()
harvest()
harvest()`

Cela vous permet de récolter plusieurs fois en une seule exécution du programme.
Cependant, il serait agréable de récolter plus de trois fois, et écrire le même code plusieurs fois est une mauvaise pratique.
La solution est une boucle.
Une boucle vous permet d'exécuter le même code plusieurs fois.

La boucle while prend une condition, qui est une valeur logique pouvant être dans l'un des deux états : `True` ou `False`.
Une telle valeur est appelée une valeur booléenne.

La boucle exécute alors le code à l'intérieur de la boucle jusqu'à ce que la condition soit False.
La boucle while ressemble à ceci :

`while condition:
	#corps de la boucle
	#corps de la boucle
	#...`

Où vous devez remplacer "condition" par une valeur booléenne et `#corps de la boucle` par ce que vous voulez faire dans la boucle.

Il y a deux valeurs booléennes constantes disponibles. Les constantes sont des valeurs qui ne changent jamais pendant le programme.

Pour créer une valeur booléenne constante qui est toujours `True`, vous pouvez simplement écrire `True`. Écrivez `False` comme une valeur booléenne constante qui sera toujours `False`.
Vous pourriez donc écrire

`while False:
	faire_un_flip()`

ou

`while True:
	faire_un_flip()`

La première ne fera jamais un flip et la seconde fera des flips à l'infini (une boucle infinie).

Normalement, créer une boucle infinie est une mauvaise idée car cela figera le programme, mais dans ce jeu, il y a des délais entre chaque itération de la boucle, donc cela fera que le drone continue de faire un flip jusqu'à ce que vous l'arrêtiez manuellement en appuyant à nouveau sur le bouton d'exécution.

Remarquez comment la ligne après les deux-points est indentée. L'indentation comme celle-ci est utilisée pour séparer les blocs de code.
Il suffit d'appuyer sur Tab pour ajouter une indentation et Shift + Tab (ou Retour arrière) pour la supprimer.

La boucle répétera toutes les instructions indentées après les deux-points.
Les instructions après le bloc indenté seront exécutées après que la boucle soit terminée.