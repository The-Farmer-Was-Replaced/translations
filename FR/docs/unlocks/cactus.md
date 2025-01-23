# Cactus
Comme les autres plantes, les [cactus](objects/cactus) peuvent être cultivés sur du sol et récoltés comme d'habitude.

Cependant, ils existent en différentes tailles et ont un sens étrange de l'ordre.

Si vous récoltez un cactus complètement mature et que tous les cactus voisins sont dans l'ordre trié, cela récoltera également tous les cactus voisins de manière récursive.

Un cactus est considéré comme étant dans l'ordre trié si tous les cactus voisins au `Nord` et à `Est` sont complètement mûrs et plus grands ou égaux, et tous les cactus voisins au `Sud` et à `Ouest` sont complètement mûrs et plus petits ou égaux.

La récolte ne se répandra que si tous les cactus adjacents sont complètement mûrs et dans l'ordre trié.
Cela signifie que si un carré de cactus mûrs est trié par taille et que vous récoltez un cactus, tout le carré sera récolté.

Vous recevrez des cactus égaux au nombre de cactus récoltés au carré. Donc, si vous récoltez `n` cactus simultanément, vous recevrez `n**2` `Items.Cactus`.

La taille d'un cactus peut être mesurée avec `measure()`.
Elle est toujours l'un de ces nombres : `0,1,2,3,4,5,6,7,8,9`.

Vous pouvez également passer une direction dans `measure(direction)` pour mesurer la tuile voisine dans cette direction du drone.

Vous pouvez échanger un cactus avec son voisin dans n'importe quelle direction en utilisant la commande `swap()`.
`swap(direction)` échange l'objet sous le drone avec l'objet une tuile dans la `direction` du drone.

<spoiler=montrer indice 1>
Si chaque colonne et chaque rangée du champ est triée, alors toutes les plantes sont en ordre trié.
</spoiler>
<spoiler=montrer indice 1>
Vous êtes récompensé pour chaque cactus qui est en ordre trié. Si certains cactus sont en ordre trié, vous obtiendrez déjà une partie de la récompense. Vous n'avez pas besoin de trier à 100%.</spoiler>
