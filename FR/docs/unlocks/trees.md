# Arbres

Les arbres sont une meilleure source de bois que les buissons. Ils donnent 5 bois chacun. Comme les buissons, ils peuvent être plantés sur de l'herbe ou du sol.

Les arbres aiment avoir de l'espace, et les planter juste à côté les uns des autres ralentira leur croissance. Le temps de croissance est doublé pour chaque arbre qui se trouve sur une case directement au `Nord`, `Est`, `Ouest` ou `Sud` de celui-ci. Donc, si vous plantez des arbres sur chaque case, ils mettront `2*2*2*2 = 16` fois plus de temps à pousser.

<spoiler=montrer> L'opérateur `%` peut être utile ici. Rappelez-vous que l'opérateur `%` renvoie le reste de la division. Les nombres pairs divisés par `2` ont un reste de `0` et les nombres impairs divisés par `2` ont un reste de `1`.

Ainsi, vous pouvez vérifier si un nombre est pair de cette manière :

`def is_even(n):
    return n % 2 == 0`

Cela renvoie `True` si n est pair et `False` si ce n'est pas le cas.
</spoiler>