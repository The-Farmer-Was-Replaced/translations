# Dictionaries
Los diccionarios son una estructura de datos que te permite mapear claves a valores de la misma manera que un diccionario real mapea palabras a sus definiciones y puedes buscarlas muy rápidamente.

Un diccionario puede ser creado así:
`rotacion = {North:East, East:South, South:West, West:North}`

La expresión antes de los dos puntos es la clave y la expresión después de los dos puntos es el valor al que la clave mapea.
El diccionario anterior mapea direcciones a la dirección a su derecha.

Aquí hay otro que mapea la posición del dron a la entidad sobre la que está.
`x, y = get_pos_x(), get_pos_y()
diccionario_entidades = {(x,y):get_entity_type()}`

Acceder al valor mapeado a una clave es similar a acceder a un elemento en una lista:
`valor = diccionario[clave]`

Ejemplo:
`orientacion = rotacion[South]`
Esto establece `orientacion` a `West`.

Puedes agregar un nuevo par clave-valor a un diccionario así:
`diccionario[clave] = valor`

Ejemplo:
`diccionario_entidades[(get_pos_x(), get_pos_y())] = get_entity_type()`
Esto actualiza la entidad almacenada para la posición actual.

Las claves son únicas, por lo que agregar una clave que ya existe en el diccionario sobrescribirá el valor anterior.

Usa `diccionario.pop(clave)` para eliminar un par clave-valor de `diccionario`.

`clave in diccionario` evalúa a `True` si `clave` es una clave en el `diccionario` y `False` en caso contrario.
Así que puedes usar `if clave in diccionario:` para verificar si `diccionario` contiene la clave.

Poner un diccionario en un bucle for te permite iterar a través de todas las claves:
`for clave in diccionario:
	valor = diccionario[clave]`

No hay garantías sobre el orden en el que se iteran las claves.

Ver también [Conjuntos](docs/scripting/sets)
