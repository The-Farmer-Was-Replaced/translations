# Name Scopes
Los alcances determinan qué variables se pueden acceder desde dónde. Un alcance es básicamente una asignación de nombres a valores.
Funcionan casi igual que en Python, pero no siempre, así que asegúrate de leer esta sección cuidadosamente.

Al igual que en Python, hay un alcance global, y cada función tiene un alcance local.
Cuando defines una variable, se agrega al alcance actual.
Cualquier cosa fuera de una definición de función se considera parte del alcance global.

`x = 1`
Asigna un valor de `1` al nombre `x` en el alcance global.

Esta declaración `def` asigna una función al nombre `f` en el alcance global.
`def f():
    `Asigna un valor de `1` al nombre `y` en el alcance local de `f`.`
    y = 1

    `Asigna una función al nombre `g` en el alcance local de `f`.`
    def g():
        pass`

`f()`
Recupera la función almacenada en `f` del alcance global y la llama.

`print(y)`
Esta declaración print en el alcance global lanza un error porque `y` nunca fue declarada en el alcance global, por lo que no podemos leerla aquí.
Solo existió en el alcance local de `f`.

Los bucles y las ramas no crean sus propios alcances, por lo que cualquier cosa declarada dentro de ellos aún se puede usar fuera.

`for i in range(3):
    pass
print(i)`

Esto imprimirá `2` porque la última iteración del bucle `for` asignó `2` a `i`.

Todo hasta aquí es lo mismo en Python. La primera diferencia está en cómo se importan las definiciones globales de otros archivos. Python usa la declaración import para esto, el juego importa funciones globales automáticamente.

Cualquier función definida en archivos cargados se agregará al alcance global antes de la ejecución, por lo que puedes usar funciones declaradas en otros archivos.
Ten en cuenta que este no es el caso para las variables globales. Solo están disponibles cuando la línea donde se asignan realmente se ejecuta. Solo se ejecutará el alcance global de la ventana en la que haces clic en el botón de ejecutar.

Las variables del alcance global se pueden leer en cualquier lugar, pero las asignaciones siempre se asignarán al alcance local.

`x = 1

def f():
    x += 1

f()

print(x)`

East código imprime `1` no `2` porque `x += 1` primero leerá `1` de la variable global `x` y luego asignará `2` a una nueva variable local que también se llama `x`.
Así que la variable global `x` nunca cambia.

East comportamiento difiere ligeramente del de Python.
Python lanza un error aquí porque estás tratando de leer de una variable local antes de que se asigne.

En Python también es posible usar la palabra clave 'global' para declarar que deseas usar la variable global en lugar de la local, pero esto no es compatible en este juego.

Si realmente necesitas actualizar variables globales, puedes usar un diccionario para ello.
Usan semántica de referencia, lo que significa que la variable contiene una referencia al diccionario subyacente, en lugar de almacenar la estructura de datos directamente en la variable.
Una variable global puede almacenar una referencia a un diccionario que se puede leer en una función.
Puedes modificar el diccionario subyacente sin actualizar la variable en el alcance global.
Dado que la variable en el alcance global aún apunta al mismo diccionario, también reflejará cualquier cambio realizado en ese diccionario. Para ilustrar, considera el siguiente código:

Asignar diccionario en el alcance global
`d = {"x": 1}

def f():
    `hacer un cambio en el diccionario al que se refiere `d`.`
    d["x"] += 1

`imprime `2
print(d["x"])`
