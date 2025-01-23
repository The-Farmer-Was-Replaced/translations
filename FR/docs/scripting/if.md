# Si
Vous pouvez utiliser `if`, `elif` et `else` pour exécuter du code conditionnellement.

`if condition1:
	do_a_flip()
elif condition2:
	harvest()
else:
	do_a_flip()
	harvest()`

## Syntaxe
Les instructions `if` vous permettent d'exécuter du code uniquement si une condition est `True`. Elles sont comme une boucle `while` qui ne boucle pas.
Le `if` prend une condition tout comme la boucle `while` et exécute le bloc de code if si la condition s'évalue à `True` :

`#effectue un flip si la condition est vraie
if condition:
	do_a_flip()`

Vous pouvez également ajouter un `else` après le if qui définit le code à exécuter si la condition est `False` :

`if condition:
	#effectue un flip si la condition est vraie
	do_a_flip()
else:
	#sinon récolte
	harvest()`

`elif` est l'abréviation de else if.

`if condition1:
	#a
else:
	if condition2:
		#b
	else:
		#c`

peut être abrégé en :

`if condition1:
	#a
elif condition2:
	#b
else:
	#c`
