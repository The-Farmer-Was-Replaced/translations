# Polyculture
Vous avez peut-être déjà remarqué que certaines plantes produisent davantage lorsqu’elles sont plantées ensemble.
L’herbe, les buissons, les arbres et les carottes donnent plus de récolte s’ils ont la bonne plante voisine. La préférence de compagnon est différente pour chaque plante et ne peut pas être prédite. Heureusement, la préférence de compagnon de la plante sous le drone peut être mesurée grâce à `get_companion()`. Cela renvoie un tuple dont le premier élément est le type de plante qu’elle souhaite en tant que compagnon et le second élément est la position où elle souhaite ce compagnon.

`plant, (x, y) = get_companion()`

Par exemple, si vous plantez un buisson, puis appelez `get_companion()`, il peut renvoyer `(Entities.Carrot, (3, 5))`. Cela signifie que ce buisson veut avoir des carottes à la position `(3,5)`. Si vous plantez des carottes à `(3,5)` puis récoltez le buisson, il fournira plus de bois. Le stade de croissance de la carotte n’a pas d’importance.

La préférence de compagnon d’une plante peut être `Entities.Grass`, `Entities.Bush`, `Entities.Tree` ou `Entities.Carrot`. Chaque plante choisit cela de façon aléatoire, mais choisira toujours un type de plante différent d’elle-même. La position peut aussi être n’importe quelle position dans un rayon de 3 déplacements, sauf la position de la plante elle-même.

S’il n’y a pas de plante sous le drone ayant une préférence de compagnon, `get_companion()` renvoie `None`.

Le multiplicateur de rendement est de `5` plus le nombre d’améliorations de polyculture.
