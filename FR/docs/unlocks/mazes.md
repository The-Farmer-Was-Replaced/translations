# Labyrinthes
`Items.Weird_Substance`, obtenu en [fertilizing](docs/unlocks/fertilizer.md) des plantes, a un effet étrange sur les buissons. Si le drone se trouve au-dessus d’un buisson et que vous appelez `use_item(Items.Weird_Substance, amount)`, le buisson se transformera en un labyrinthe de haies.
La taille du labyrinthe dépend de la quantité de `Items.Weird_Substance` utilisée (le second argument de l’appel `use_item()`).
Sans améliorations de labyrinthe, l’utilisation de `n` `Items.Weird_Substance` résultera en un labyrinthe de `n`x`n`. Pour chaque niveau d’amélioration, il faut utiliser `n` `Items.Weird_Substance` supplémentaires pour obtenir le même effet.
Ainsi, pour créer un labyrinthe qui occupe tout le champ :

`plant(Entities.Bush)
n_substance = get_world_size() * num_unlocked(Unlocks.Mazes)
use_item(Items.Weird_Substance, n_substance)`

Pour une raison inconnue, le drone ne peut pas voler au-dessus des haies, même si elles ne semblent pas très hautes.

Un trésor est caché quelque part dans la haie. Utilisez `harvest()` sur le trésor pour recevoir une quantité d’or égale à la superficie du labyrinthe. (Par exemple, un labyrinthe de 5x5 procurera 25 or.)

Si vous utilisez `harvest()` n’importe où ailleurs, le labyrinthe disparaîtra simplement.

`get_entity_type()` est égal à `Entities.Treasure` si le drone se trouve sur le trésor, et `Entities.Hedge` partout ailleurs dans le labyrinthe.

Les labyrinthes ne contiennent aucune boucle à moins que vous ne réutilisiez le labyrinthe (voir plus bas comment réutiliser un labyrinthe). Il n’y a donc aucun moyen de revenir à la même position sans faire demi-tour.

Vous pouvez vérifier s’il y a un mur en essayant de le traverser.
`move()` renvoie `True` si le déplacement a réussi, et `False` sinon.

Si vous n’avez aucune idée de comment atteindre le trésor, consultez l’indice 1. Il vous indique comment aborder ce genre de problème.

Pour relever un défi supplémentaire, vous pouvez également réutiliser le labyrinthe en appliquant de nouveau la même quantité de `Items.Weird_Substance` sur le trésor.
Ceci augmentera la quantité d’or dans le trésor d’un labyrinthe complet et déplacera le trésor à une position aléatoire dans le labyrinthe.

Lorsque vous utilisez `measure()` sur un trésor, vous obtenez la position à laquelle il se déplacera, sous forme de tuple :
`next_x, next_y = measure()`

Chaque fois que le trésor est déplacé, un mur aléatoire peut être supprimé du labyrinthe. Ainsi, les labyrinthes réutilisés peuvent comporter des boucles.

Notez que la présence de boucles dans le labyrinthe complique fortement la situation, car vous pouvez atteindre à nouveau la même position sans revenir sur vos pas.
La réutilisation du labyrinthe ne rapporte pas plus d’or que de simplement le récolter et en créer un nouveau.
C’est à 100% un défi supplémentaire que vous pouvez tout à fait ignorer.
Cela ne vaut la peine que si les informations supplémentaires et les raccourcis vous aident à résoudre le labyrinthe plus rapidement.

Le même labyrinthe peut être résolu un maximum de 300 fois. Cela correspond à 299 déplacements du trésor. Après cela, l’utilisation de weird substance sur le trésor n’aura plus aucun effet.

<spoiler=show hint 1>Voici une approche générale pour résoudre le problème :

Créez un labyrinthe et imaginez que vous êtes le drone.

Réfléchissez à la manière dont vous chercheriez le trésor si vous étiez dans le labyrinthe.

Décrivez votre stratégie étape par étape de sorte que quelqu’un d’autre puisse la suivre sans réfléchir.

Ensuite, essayez de traduire ces étapes en code.
</spoiler>
<spoiler=show hint 2>Tant qu’il n’y a pas de boucles : tous les murs forment essentiellement un seul mur connecté. Si vous suivez ce mur, vous traverserez tout le labyrinthe.
Cette méthode requiert très peu de code et vous n’avez pas besoin de garder une trace de vos déplacements antérieurs. Une dizaine de lignes de code suffit.</spoiler>
<spoiler=show hint 3>Au lieu de se déplacer dans des directions absolues comme `East` ou `West`, il peut être très utile de se déplacer avec des directions relatives, par exemple « tourner à droite » ou « tourner à gauche ». Pour ce faire, vous devez garder en mémoire la direction actuelle du drone. Le drone ne tourne jamais réellement, mais vous pouvez quand même gérer une « rotation virtuelle » dans le code.
L’astuce d’index suivante peut vous aider :

`directions = [North, East, South, West]
index = 0`

Utilisez `% 4` pour « tourner en rond », de sorte qu’après `West` on revienne à `North` :
`# turn right
index = (index + 1) % 4`

`# turn left
index = (index - 1) % 4

move(directions[index])`
</spoiler>
<spoiler=show hint 4>Si vous ne parvenez pas à le résoudre, vous pouvez toujours vous faciliter la tâche et procéder de manière moins efficiente.
Résoudre un labyrinthe de `1`x`1` est trivial.
</spoiler>
