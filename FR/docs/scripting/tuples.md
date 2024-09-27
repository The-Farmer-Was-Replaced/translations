# Tuples

Les tuples sont un excellent moyen de combiner plusieurs valeurs en une seule valeur.
Pour créer un tuple, il suffit de séparer les valeurs par des virgules :

`tuple = 1, 2`

Vous pouvez également les décompresser dans plusieurs variables à nouveau. Dans le code ci-dessous, le tuple `(1,2)` est décompressé en deux variables `a` et `b`.

`a, b = 1, 2`

Les tuples peuvent être indexés comme des listes, mais ils sont immuables et ne peuvent pas être modifiés après leur création.

`tuple = 1, 2`

`print(tuple[1])`
affiche `2`

`tuple[0] = 3`
provoque une erreur

<unlock=dicts>
Contrairement aux listes, les tuples peuvent être utilisés comme clés dans les dictionnaires.

`d = {(1,2):(4,5)}

print(d[(1,2)])`
`affiche` (4,5)</unlock>

Ils peuvent également être utiles pour retourner plusieurs valeurs dans une fonction.

`def f():
    return 1, 2

a, b = f()`