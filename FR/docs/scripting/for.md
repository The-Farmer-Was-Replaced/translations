# Boucle For

La boucle `for` fonctionne comme en Python. (Appelée une boucle foreach dans certains langages, à ne pas confondre avec la boucle for de style C, qui est différente).

`for i in sequence:
	#do something with i`

Similaire à la boucle `while`, la boucle `for` appelle également de manière répétée un bloc de code. Au lieu de boucler en fonction d'une condition, elle exécute le corps de la boucle une fois pour chaque élément d'une séquence.

## Syntaxe

Une boucle for ressemble à ceci :

`for variable_name in sequence:
	#code block`

`variable_name` peut être n'importe quel nom que vous choisissez. C'est une variable qui stocke l'élément actuel dans la séquence. `sequence` doit être une valeur qui peut être itérée, comme une plage ou des nombres. Le bloc de code est exécuté pour chaque élément avec la variable de boucle assignée à cet élément.

## Séquences

[Plages](functions/range) <unlock=lists>[Listes](docs/scripting/lists.md) </unlock><unlock=functions>[Tuples](docs/scripting/tuples.md) </unlock><unlock=dicts>[Dictionnaires](docs/scripting/dicts.md) </unlock><unlock=sets>[Ensembles](docs/scripting/sets.md)</unlock>

## Exemple

`for i in range(5):
    harvest()`

Cette boucle exécute le corps un nombre fixe de fois. C'est essentiellement la même chose que d'écrire

`i = 0
harvest()
i = 1
harvest()
i = 2
harvest()
i = 3
harvest()
i = 4
harvest()`

Ainsi, elle appelle `harvest()` 5 fois.

Voir aussi [Break](docs/scripting/break) et [Continue](docs/scripting/continue)