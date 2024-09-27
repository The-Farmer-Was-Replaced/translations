# Lists
Las listas son una forma fácil de almacenar múltiples valores en una sola variable.
Puedes crear nuevas listas así:

`lista = [2, True, Items.Hay]`

La lista ahora contiene los valores `2`, `True` y `Items.Hay`.
Una lista también puede estar vacía:

`lista_vacia = []`

Puedes acceder a un elemento de una lista por su índice. El índice es `0` para el primer elemento, `1` para el segundo elemento, `2` para el tercero...

plantar zanahorias
`lista = [Entities.Tree, Entities.Carrots, Entities.Pumpkin]
plantar(lista[1])`

Puedes iterar sobre una lista usando un bucle for. El siguiente ejemplo suma todos los elementos en la lista.

`lista = [4, 7, 2, 5]
suma = 0
for numero in lista:
	suma += numero`
`suma` es ahora `18`

Los siguientes métodos de lista te permiten agregar y eliminar elementos:

`lista.append(elem)` agrega un elemento al final de la lista:

`lista = [2, 6, 12]
lista.append(7)`
`lista` es ahora `[2, 6, 12, 7]`

`lista.remove(elem)` elimina la primera ocurrencia de un elemento de una lista:

`lista = [1, 2, 4, 2]
lista.remove(2)`
`lista` es ahora `[1, 4, 2]`

`lista.insert(index, elem)` inserta un elemento en el índice dado:

`lista = [Entities.Tree, Items.Hay]
lista.insert(1, Items.Wood)`
`lista` es ahora `[Entities.Tree, Items.Wood, Items.Hay]`

`lista.pop(index)` elimina el elemento en el índice especificado.
Si no se especifica un índice, se elimina el último elemento.

`lista = [3, 5, 8, 25]
lista.pop()`
`lista` es ahora `[3, 5, 8]`
`lista.pop(1)`
`lista` es ahora `[3, 8]`

La función `len()` devuelve la longitud de la lista.
`lista = [3, 2, 1]
x = len(lista)`
`x` es ahora `3`

Las listas tienen semántica de referencia. Esto significa que asignar una lista a una variable asigna el mismo objeto de lista a esa variable, en lugar de hacer una copia de la lista.
Si dos variables hacen referencia a la misma lista, los cambios en la lista serán vistos por ambas.

`a = [1,2]
b = a
b.pop()`
`a` y `b` son ahora ambos `[1]`

