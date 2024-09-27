# Polyculture

L'herbe, les buissons, les arbres et les carottes produisent dix fois plus lorsqu'ils ont le bon compagnon de plante. La préférence de compagnon est différente pour chaque plante individuelle et ne peut pas être prédite. Heureusement, la préférence de compagnon de la plante sous le drone peut être mesurée en utilisant `get_companion()`. Cela renvoie une liste où le premier élément est le type de plante qu'elle souhaite avoir comme compagnon et les deuxième et troisième éléments sont les coordonnées x et y de la position où elle souhaite son compagnon.

Par exemple, si vous plantez un buisson et appelez ensuite `get_companion()`, cela renverra quelque chose comme `[Entities.Carrots, 3, 5]`. Cela signifie que ce buisson aimerait avoir des carottes à la position `(3,5)`. Donc, si vous plantez des carottes à `(3,5)` et récoltez ensuite le buisson, il produira dix fois plus de bois. Le stade de croissance de la carotte n'a pas d'importance.

La préférence de compagnon d'une plante peut être soit `Entities.Grass`, `Entities.Bush`, `Entities.Tree` ou `Entities.Carrots`. Chaque plante choisit cela au hasard, mais elle choisira toujours une plante différente d'elle-même. La position peut également être n'importe quelle position à 3 mouvements de la plante, sauf la position de la plante elle-même.

S'il n'y a pas de plante sous le drone qui ait une préférence de compagnon, `get_companion()` renverra `None`. 
