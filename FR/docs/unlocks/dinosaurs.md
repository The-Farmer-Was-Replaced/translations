# Dinosaures

Les dinosaures sont des créatures anciennes et majestueuses qui peuvent être cultivées pour obtenir des os anciens.

Pour obtenir des dinosaures, vous devez échanger des œufs et les utiliser avec `use_item(Items.Egg)`.

Les dinosaures aiment se déplacer. De temps en temps, le dinosaure échangera sa place avec un voisin aléatoire. Cet échange fonctionne exactement comme si vous appeliez `swap(direction)` manuellement, sauf qu'il se produit de manière aléatoire de temps en temps.

Les dinosaures peuvent être récoltés pour obtenir des os en utilisant la commande `harvest()`.

Il existe 4 types différents de dinosaures. Récolter un dinosaure récoltera également tous les dinosaures adjacents du même type, de sorte qu'un groupe entier de dinosaures connectés sera récolté en une seule fois.

Le type d'un dinosaure peut être mesuré avec `measure()`. Cela renverra un numéro unique pour chaque type de dinosaure.

N'oubliez pas que vous pouvez également passer une direction dans measure pour mesurer une entité à côté du drone. `measure(North)` par exemple mesurera l'entité au nord du drone.

Le nombre d'os que vous obtenez dépend de la taille du groupe de dinosaures que vous récoltez. Récolter des groupes jusqu'à 4 laissera tomber des os égaux au carré de la taille du groupe. Les groupes de taille 4 ou plus laissent tomber des os égaux à 4 fois la taille du groupe.

Ainsi, le nombre d'os par dinosaure augmente avec la taille du groupe jusqu'à la taille 4, puis reste constant. Pour une efficacité optimale, vous voulez toujours récolter des groupes de taille 4 ou plus.

Les groupes s'enroulent également autour du côté de la ferme. Ainsi, un dinosaure au bord de la ferme est considéré comme adjacent à un dinosaure de l'autre côté de la ferme.