# Labyrinthes

Si vous utilisez de l'engrais sur un buisson entièrement développé, il se transformera en un labyrinthe de haies avec une probabilité de 10%. Pour une raison quelconque, le drone ne peut pas survoler les haies, même si elles ne semblent pas si hautes.

Il y a un trésor caché quelque part dans la haie. Utilisez `harvest()` sur le trésor pour recevoir de l'or égal à la superficie du labyrinthe. (Par exemple, un labyrinthe de 5x5 donnera 25 pièces d'or.)

Si vous utilisez `harvest()` ailleurs, le labyrinthe disparaîtra simplement.

`get_entity_type()` est égal à `Entities.Treasure` si le drone est au-dessus du trésor et `Entities.Hedge` partout ailleurs dans le labyrinthe.

Les labyrinthes ne contiennent pas de boucles à moins que vous ne réutilisiez le labyrinthe (voir ci-dessous comment réutiliser un labyrinthe). Ainsi, il n'y a aucun moyen pour le drone de se retrouver à nouveau dans la même position sans revenir en arrière.

Vous pouvez vérifier s'il y a un mur en essayant de le traverser. 
`move()` renvoie `True` s'il a réussi et `False` sinon.

Si vous n'avez aucune idée de comment atteindre le trésor, jetez un œil à l'indice 1. Il vous montre comment aborder un problème comme celui-ci.

Pour un défi supplémentaire, vous pouvez également réutiliser le labyrinthe en utilisant de l'engrais sur le trésor. 
Cela a une probabilité de 10% d'augmenter le trésor d'un labyrinthe complet et de le déplacer à une position aléatoire dans le labyrinthe.
Utiliser `measure()` sur un trésor renvoie la position où il ira ensuite sous forme de tuple `(x_position, y_position)`.

Par exemple, au-dessus du trésor, le code suivant vous donne la position où le trésor sera après l'avoir fertilisé :
`next_x, next_y = measure()`

Chaque fois que le trésor est relocalisé, un mur aléatoire peut être retiré du labyrinthe. Ainsi, les labyrinthes réutilisés peuvent contenir des boucles.

Notez que les boucles dans le labyrinthe le rendent beaucoup plus difficile, donc si vous êtes débutant, vous ne voudrez peut-être pas réutiliser les labyrinthes. Réutiliser les labyrinthes ne vous donne pas plus d'or que de générer un nouveau labyrinthe. Cela vaut seulement la peine si les informations supplémentaires et les raccourcis vous aident à résoudre le labyrinthe plus rapidement.

Le même labyrinthe peut être résolu un maximum de 300 fois. Cela correspond à 299 relocalisations. Après cela, fertiliser le trésor n'aura plus aucun effet.

<spoiler=montrer l'indice 1>Voici une approche générale pour résoudre le problème :

Créez un labyrinthe et imaginez que vous êtes le drone.

Réfléchissez à la façon dont vous essayeriez de trouver le trésor si vous étiez dans le labyrinthe.

Écrivez votre stratégie étape par étape afin que quelqu'un d'autre puisse la suivre sans réfléchir.

Essayez maintenant de traduire vos étapes en code.
</spoiler>
<spoiler=montrer l'indice 2>Pour les labyrinthes sans cycles : Tous les murs ne sont vraiment qu'un grand mur connecté. Si vous suivez le mur, il vous guidera à travers tout le labyrinthe.</spoiler>
<spoiler=montrer l'indice 3>Il peut être utile de suivre la direction vers laquelle le drone est orienté afin que vous puissiez faire des virages à gauche et à droite. Le drone ne tourne jamais réellement, mais vous pouvez toujours garder une "rotation virtuelle" dans le code.
L'astuce d'index suivante pourrait être utile pour cela :

`directions = [North, East, South, West]`
`index = 0`

`# tourner à droite`
`# le % 4 le fait boucler`
`index = (index + 1) % 4`

`# tourner à gauche`
`index = (index - 1) % 4`

`move(directions[index])`
</spoiler>
<spoiler=montrer l'indice 4>Si vous ne pouvez pas le résoudre, vous pouvez toujours vous faciliter la vie et le faire moins efficacement.
Vous n'avez pas besoin de pouvoir atteindre le trésor à chaque fois, vous pouvez toujours récolter et générer un nouveau labyrinthe.
Il y a même une petite chance que le trésor apparaisse juste sous le drone lorsque vous créez un labyrinthe.</spoiler>