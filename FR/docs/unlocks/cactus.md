# Cactus
Les cactus peuvent être cultivés sur du sol à partir de graines de cactus.

Ils ont un sens étrange de la communauté.

Lorsque vous récoltez un cactus, tous les cactus du champ sont récoltés. Le nombre d'éléments de cactus tombés par cactus est égal à la taille du monde telle que renvoyée par `get_world_size()`.

Un cactus ne laisse tomber des éléments de cactus lors de la récolte que s'il est en ordre trié. 
Un cactus est considéré comme étant en ordre trié s'il y a un cactus plus petit ou égal au `Sud` et à l'`Ouest` et un cactus plus grand ou égal au `Nord` et à l'`Est`.
Essentiellement, les cactus doivent être triés dans les directions x et y croissantes pour qu'ils laissent tomber quoi que ce soit.

Si un cactus est au bord du champ, seuls les champs voisins existants doivent être corrects pour qu'il soit trié.

La taille d'un cactus peut être mesurée avec `measure()`. 
Elle est toujours l'un de ces nombres : `0,1,2,3,4,5,6,7,8,9`.

Vous pouvez également passer une direction dans `measure(dir)` pour mesurer la tuile voisine dans cette direction du drone.

Vous pouvez échanger un cactus avec son voisin dans n'importe quelle direction en utilisant la commande `swap()`.
`swap(direction)` échange l'objet sous le drone avec l'objet à une tuile dans la `direction` du drone.

<spoiler=montrer indice 1>
Si chaque colonne et chaque rangée du champ est triée, alors toutes les plantes sont en ordre trié.
</spoiler>
<spoiler=montrer indice 1>
Vous êtes récompensé pour chaque cactus qui est en ordre trié. Si certains cactus sont en ordre trié, vous obtiendrez déjà une partie de la récompense. Vous n'avez pas besoin de trier à 100%.</spoiler>