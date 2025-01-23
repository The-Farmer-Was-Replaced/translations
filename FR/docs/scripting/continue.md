# Continue

`continue` permet d'arrêter l'itération actuelle d'une boucle et de passer à l'itération suivante de la boucle la plus interne.

`for i in range(10):
	continue
    print("ceci n'est jamais imprimé")`

Cela exécute toutes les `10` itérations de la boucle, mais l'instruction `print` après le `continue` est toujours ignorée.

Cela fonctionne également avec les boucles `while`.

`while True:
	if not can_harvest():
		continue

	harvest()`

Ce code appelle `harvest()` uniquement lorsque `can_harvest()` est `True`.
Il a le même effet que

`while True:
	if can_harvest():
		harvest()`

Dans les boucles imbriquées, `continue` affecte toujours la boucle la plus interne.

`for i in range(10):
	for j in range(10):
	    print("ceci est imprimé 100 fois")
		continue
		print("ceci n'est jamais imprimé")
	print("ceci est imprimé 10 fois")`
