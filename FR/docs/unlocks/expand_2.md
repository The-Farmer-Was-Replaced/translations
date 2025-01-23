# Étendre 2
Votre ferme s’est encore agrandie ! Désormais, les parcelles ne sont plus alignées en une seule rangée, vous devez donc trouver un moyen de parcourir une grille carrée.

Avec la boucle `while`, ce n’est pas possible tant que vous n’avez pas débloqué les sens et les opérateurs.
Il est temps d’introduire la boucle `for`.

Vous pouvez tout lire à propos de la boucle `for` sur la page [For Loop](docs/scripting/for.md), mais pour l’instant, vous n’en aurez besoin que pour répéter du code un nombre fixe de fois.

`#do n flips
for i in range(5):
	do_a_flip()`

`range(n)` crée une plage de nombres de `0` à `n-1` qui contient `n` éléments. La boucle `for` exécute son corps une fois pour chaque élément de la séquence. Dans cet exemple, `do_a_flip()` sera appelé 5 fois.

La fonction `get_world_size()` est également disponible maintenant. Elle renvoie la taille de votre ferme, ce qui permet d’écrire du code qui ne se brisera pas lors de la prochaine extension.

`for i in range(get_world_size()):
	harvest()
	move(North)`

Cet exemple récolte une colonne de la ferme pour n’importe quelle taille de ferme.

Si vous êtes bloqué pour trouver comment déplacer le drone sur la ferme, consultez l’indice ci-dessous.
<spoiler=show hint>Il existe bien sûr plusieurs façons de se déplacer sur la ferme.
Nous recherchons un moyen systématique qui ne cassera pas lors du prochain agrandissement.
Un moyen systématique d’atteindre chaque endroit de la ferme est de répéter ces deux étapes à l’infini :

1. Se déplacer vers le `North` jusqu’à boucler.
2. Se déplacer vers l’`East`.

`for i in range(get_world_size()):` peut aider à concrétiser cette idée en code.
</spoiler>
<spoiler=show possible solution>Un parcours de base pourrait ressembler à :

`for i in range(get_world_size()):
	for j in range(get_world_size()):
		#do a flip on every tile
		do_a_flip()
		move(North)
	move(East)`
</spoiler>
