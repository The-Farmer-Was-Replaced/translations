# Dinosaures
Les dinosaures sont des créatures anciennes et majestueuses qui peuvent être élevées pour obtenir des ossements anciens.

Malheureusement, les dinosaures ont disparu il y a longtemps, donc le mieux que nous puissions faire maintenant est de se déguiser en l'un d'eux.
À cet effet, vous avez reçu le nouveau chapeau de dinosaure.

Le chapeau peut être équipé avec
`change_hat(Hats.Dinosaur_Hat)`

Malheureusement, il ne ressemble pas tout à fait à la publicité...

Si vous équipez le chapeau de dinosaure et que vous avez suffisamment de citrouilles, une [pomme](objects/apple) sera automatiquement achetée et placée sous le drone.
Chaque fois que vous vous éloignez d'une pomme, la queue du chapeau de dinosaure grandira d'une tuile et, si vous avez suffisamment d'objets, une nouvelle pomme sera achetée et placée à un endroit aléatoire.
La pomme ne peut pas apparaître si quelque chose est déjà planté là où elle veut être.

La queue du dinosaure sera traînée derrière le drone remplissant les tuiles précédentes sur lesquelles le drone s'est déplacé. Si un drone essaie de se déplacer sur la queue, `move()` échouera et renverra `False`.
Le dernier segment de la queue se déplacera pour faire place pendant le déplacement, vous permettant de vous y déplacer. Cependant, si le serpent remplit tout la ferme, vous ne pourrez plus vous déplacer. Vous pouvez donc vérifier si le serpent est complètement développé en vérifiant si vous ne pouvez plus vous déplacer.

Utiliser `measure()` sur une pomme renverra la position de la prochaine pomme sous forme de tuple.

`next_x, next_y = measure()`

Lorsque le chapeau est de nouveau déséquippé en équipant un autre chapeau, la queue sera récoltée.
Vous recevrez des os égaux au carré de la longueur de la queue. Donc, pour une queue de longueur `n`, vous recevrez `n**2` `Items.Bone`.
Par exemple :
longueur 1 => 1 os
longueur 2 => 4 os
longueur 3 => 9 os
longueur 4 => 16 os
longueur 16 => 256 os
longueur 100 => 10000 os

Le Chapeau de Dinosaure est très lourd, donc si vous l'équipez, `move()` prendra 800 ticks au lieu de 200. Cependant, chaque fois que vous ramassez une pomme, le nombre de ticks utilisés par `move()` est réduit de 3 % (arrondi vers le bas), car une queue plus longue peut vous aider à vous déplacer.

La boucle suivante affiche le nombre de ticks utilisés par `move()` après n'importe quel nombre de pommes :

`ticks = 800
for i in range(100):
    print("ticks after ", i, " apples: ", ticks)
    ticks -= ticks * 0.03 // 1`

<spoiler=afficher l'indice 1>Si vous continuez à vous déplacer le long du même chemin qui couvre tout le champ, vous pouvez facilement obtenir un serpent de champ complet à chaque fois, car vous couvrirez chaque endroit libre avant de revenir à l'endroit où se trouve votre queue. Ce n'est pas très efficace, mais ça fonctionne.</spoiler>
