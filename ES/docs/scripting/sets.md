# Sets
Los conjuntos son como [diccionarios](docs/scripting/dicts), pero sin valores. Son solo un conjunto desordenado de claves.

Se crean como diccionarios, pero sin valores.
`set = {North, East, West}`

Usa `set.add(elem)` para agregar un nuevo elemento al conjunto.

Usa `set.remove(elem)` para eliminar un elemento del conjunto.

Usa `if elem in set:` para verificar si el conjunto contiene un elemento.

Usa `for elem in set:` para iterar todos los elementos del conjunto.
Para conjuntos más grandes, el operador `in` funciona mucho más rápido que en una lista.

Al igual que los diccionarios, los conjuntos son desordenados, por lo que no hay garantías sobre el orden en que se iteran los elementos.

Además, los elementos en los conjuntos son únicos, por lo que agregar un elemento que ya está en el conjunto no cambiará el conjunto.
