# Fonctions
Utilisez le mot-clé `def` pour définir une nouvelle fonction :
`def f(arg1, arg2 = False):
	#code de la fonction`

Vous pouvez utiliser l'opérateur d'appel `()` pour appeler la fonction :
`f(42)`

Contrairement à Python, les fonctions définies dans la portée globale de n'importe quel fichier ouvert peuvent être appelées par leur nom, même si l'instruction `def` n'a jamais été exécutée.
Voir [Portées](docs/scripting/scopes.md) pour plus d'informations à ce sujet.

## Introduction
Vous avez déjà vu des fonctions intégrées comme `harvest()`.
Vous pouvez également définir vos propres fonctions, ce qui permet de structurer votre code de manière modulaire. Cela vous permet essentiellement de donner un nom à un bloc de code afin que vous puissiez l'appeler de n'importe où.

## Définitions de Fonction
Par exemple, vous pourriez définir une fonction qui déplace le drone plusieurs fois.

`def move_n_dir(n, dir):
	for i in range(n):
		move(dir)`

Le mot-clé `def` indique qu'il s'agit d'une définition de fonction.
`move_n_dir` est le nom auquel la fonction est liée. Cela peut être n'importe quel nom de variable valide et sera utilisé pour appeler la fonction.
`n` et `dir` sont des paramètres. Ce sont des variables qui contiennent les valeurs passées à la fonction (ces valeurs sont également appelées arguments). Vous pouvez ajouter autant de paramètres à une définition de fonction que vous le souhaitez.
Après le `:` vient le bloc de code qui s'exécutera lorsque la fonction sera appelée.

Avec la définition ci-dessus, le code suivant déplace ensuite le drone de `10` cases vers le `Nord` et de `2` cases vers l'`Ouest`.

`move_n_dir(10, North)
move_n_dir(2, West)`

## Valeurs de Retour
Utilisez le mot-clé `return` pour qu'une fonction renvoie une valeur.
Par exemple, la fonction suivante définit l'opération ou exclusif. L'ou exclusif renvoie `True` si une valeur est `True` et l'autre est `False` :

`def xor(a, b):
	return a != b

if xor(True, False):
	do_a_flip()`

[Tuples](docs/scripting/tuples.md) permettent de renvoyer plusieurs valeurs.

## Arguments par Défaut
Vous pouvez également attribuer des valeurs par défaut qui seront utilisées si aucun argument n'est passé.

`def f(a = False):
	if a:
		do_a_flip()

f()

f(True)`

Un argument qui a une valeur par défaut ne peut pas être suivi par un argument qui n'a pas de valeur par défaut.

## Utilisation Avancée des Fonctions
Les fonctions sont des valeurs comme n'importe quelle autre valeur, et l'instruction `def` agit simplement comme une instruction d'affectation, assignant la fonction au nom que vous lui donnez.
Cela permet de faire des choses comme ceci :

`def f():
	def d():
		do_a_flip()
	return d

f()()`

Ici, `f()` appelle la fonction `f` qui définit et renvoie une nouvelle fonction `d`. Le second `()` exécute ensuite la fonction renvoyée et effectue un flip.
(Faire ce genre de choses n'est généralement pas une bonne idée car il est difficile de voir ce qui se passe)

Les fonctions qui prennent d'autres fonctions comme arguments vous permettent d'être vraiment créatif :

`def f(g, arg):
	for _ in range(10):
		g(arg)

f(move, North)
f(use_item, Items.Fertilizer)`

Ce code déplace le drone `North` 10 fois et utilise ensuite l'engrais 10 fois.