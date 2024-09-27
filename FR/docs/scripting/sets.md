# Ensembles

Les ensembles sont comme les [dictionnaires](docs/scripting/dicts), mais sans valeurs. Ce sont juste un ensemble non ordonné de clés.

Ils sont créés comme des dictionnaires, mais sans valeurs.
`set = {Nord, Est, Ouest}`

Utilisez `set.add(elem)` pour ajouter un nouvel élément à l'ensemble.

Utilisez `set.remove(elem)` pour retirer un élément d'un ensemble.

Utilisez `if elem in set:` pour vérifier si l'ensemble contient un élément.

Utilisez `for elem in set:` pour itérer tous les éléments de l'ensemble.
Pour les ensembles plus grands, l'opérateur `in` fonctionne beaucoup plus rapidement que sur une liste.

Tout comme les dictionnaires, les ensembles sont non ordonnés, donc il n'y a aucune garantie sur l'ordre dans lequel les éléments sont itérés.

De plus, les éléments dans les ensembles sont uniques, donc ajouter un élément qui est déjà dans l'ensemble ne changera pas l'ensemble.