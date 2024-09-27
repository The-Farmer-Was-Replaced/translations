# Pause

`break` permet d'arrêter une boucle prématurément. Lorsque l'instruction `break` est atteinte, elle sort immédiatement de la boucle la plus interne et commence à exécuter le code après la boucle.

`for i in range(10):
	break
print(i)`

Cela affiche `0` parce que `i` est `0` lors de la première itération de la boucle, puis l'instruction break met fin à la boucle.

Cela fonctionne également avec les boucles `while`.

`while True:
	if can_harvest():
		break`

Ce code exécute la boucle `while` jusqu'à ce que `can_harvest()` soit `True`.
Cela a le même effet que

`while not can_harvest():
	pass`

Dans les boucles imbriquées, `break` sort toujours de la boucle la plus interne.

`for i in range(10):
	for j in range(10):
		break
		print("this is never printed")
	print("this is printed 10 times")`