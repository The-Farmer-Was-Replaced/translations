# Expansion 2

Votre ferme s'est encore agrandie ! Maintenant, les cases ne sont plus alignées en une belle rangée, vous devez donc trouver un moyen de traverser une grille carrée.

Avec la boucle `while`, cela n'est pas possible tant que vous n'avez pas débloqué les sens et les opérateurs. Il est temps d'introduire la boucle `for`.

Vous pouvez tout lire sur la boucle `for` sur la page [Boucle For](docs/scripting/for), mais pour l'instant, vous n'en aurez besoin que pour répéter du code un nombre fixe de fois.

`#faire n flips
for i in range(5):
	do_a_flip()`

`range(n)` crée une plage de nombres de `0` à `n-1`, qui contient `n` éléments. La boucle `for` exécute son corps de boucle une fois pour chaque élément de la séquence. Dans cet exemple, `do_a_flip()` sera appelé `5` fois.

La fonction `get_world_size()` est également disponible maintenant. Elle renvoie la longueur du côté de votre ferme. De cette façon, vous pouvez écrire du code qui ne se cassera pas avec la prochaine mise à jour d'expansion.

`for i in range(get_world_size()):
	harvest()
	move(North)`

Cet exemple récolte une colonne de la ferme pour n'importe quelle taille de ferme.

Si vous êtes bloqué en essayant de comprendre comment déplacer le drone autour de la ferme, consultez l'indice ci-dessous.
<spoiler=montrer l'indice>Il existe, bien sûr, plusieurs façons de se déplacer autour de la ferme.
Ce que nous recherchons, c'est une façon de la traverser de manière systématique qui ne se cassera pas lorsque la ferme grandira à nouveau.
Une manière systématique d'atteindre chaque endroit de la ferme serait de répéter les deux étapes suivantes à l'infini :

1. Déplacez-vous vers le `Nord` jusqu'à ce qu'il revienne.
2. Déplacez-vous vers l'`Est`

`for i in range(get_world_size()):` peut être utile pour transformer cette idée en code.
</spoiler>
<spoiler=montrer une solution possible> Le parcours de base pourrait ressembler à ceci :

`for i in range(get_world_size()):
	for j in range(get_world_size()):
		#do a flip on every tile
		do_a_flip()
		move(North)
	move(East)`
</spoiler>