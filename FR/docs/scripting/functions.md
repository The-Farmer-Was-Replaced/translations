# Fonctions
Utilisez le mot-clé `def` pour définir une nouvelle fonction :
`def f(arg1, arg2 = False):
	#function code`

Vous pouvez utiliser l'opérateur d'appel `()` pour appeler la fonction :
`f(42)`

Voir également [Scopes](docs/scripting/scopes.md) pour en savoir plus sur les variables locales et globales dans les fonctions.

## Introduction
Vous avez déjà vu des fonctions intégrées comme `harvest()`.
Vous pouvez également définir vos propres fonctions, ce qui permet de structurer votre code de manière modulaire. En gros, cela vous permet de donner un nom à un bloc de code afin de pouvoir l'appeler depuis n'importe où.

## Définitions de Fonctions
Par exemple, vous pourriez définir une fonction qui déplace le drone plusieurs fois.

`def move_n_dir(n, dir):
	for i in range(n):
		move(dir)`

Le mot-clé `def` indique qu'il s'agit d'une définition de fonction.
`move_n_dir` est le nom auquel la fonction est liée. Cela peut être n'importe quel nom de variable valide et sera utilisé pour appeler la fonction.
`n` et `dir` sont des paramètres. Ce sont des variables qui contiennent les valeurs passées à la fonction (Ces valeurs sont également appelées arguments). Vous pouvez ajouter autant de paramètres à une définition de fonction que vous le souhaitez.
Après les `:` vient le bloc de code qui sera exécuté lorsque la fonction est appelée.

Avec la définition ci-dessus, le code suivant déplace le drone de `10` tuiles `North` et `2` tuiles `West`.

`move_n_dir(10, North)
move_n_dir(2, West)`

Lorsque vous voyez `def function():`, vous devriez vraiment le considérer comme une affectation de variable comme ceci :
`function = create_new_function_object()`
Comme avec toutes les affectations, vous ne pouvez pas utiliser la variable avant qu'elle ne soit assignée !
La déclaration `def` doit s'exécuter avant tout appel de fonction.
Cela ne fonctionnera pas :

`func()
def func():
	pass`

## Valeurs de Retour
Utilisez le mot-clé `return` pour faire en sorte qu'une fonction renvoie une valeur.
Par exemple, la fonction suivante définit l'opération XOR exclusive. Le XOR exclusif renvoie `True` si une valeur est `True` et l'autre est `False` :

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

Un argument qui a une valeur par défaut ne peut pas être suivi d'un argument qui n'a pas de valeur par défaut.

## Utilisation Avancée des Fonctions
Les fonctions sont des valeurs tout comme n'importe quelle autre valeur, et l'instruction `def` agit comme une instruction d'affectation, assignant la fonction au nom que vous lui donnez.
Cela permet de faire des choses comme ceci :

`def f():
	def d():
		do_a_flip()
	return d

f()()`

Ici, `f()` appelle la fonction `f` qui définit et renvoie une nouvelle fonction `d`. Les secondes `()` exécutent ensuite la fonction renvoyée et effectuent le flip.
(Faire ce genre de choses n'est généralement pas une bonne idée car il est difficile de voir ce qui se passe)

Les fonctions qui prennent d'autres fonctions comme arguments vous permettent d'être vraiment créatif :

`def f(g, arg):
	for _ in range(10):
		g(arg)

f(move, North)
f(use_item, Items.Fertilizer)`

Ce code déplace le drone `North` 10 fois puis utilise de l'engrais 10 fois.
