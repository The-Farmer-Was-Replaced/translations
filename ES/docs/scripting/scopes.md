# Ámbitos de Nombres
Los ámbitos determinan qué variables pueden ser accesibles desde dónde. Un ámbito es básicamente un mapeo de nombres a valores.
Funcionan básicamente igual que en Python.

Hay un ámbito global y cada función tiene un ámbito local.
Cuando defines una variable, se añade al ámbito actual.
Cualquier cosa fuera de una definición de función se considera parte del ámbito global.

`x = 1`
Asigna un valor de `1` al nombre `x` en el ámbito global.

Esta declaración `def` asigna una función al nombre `f` en el ámbito global.
`def f():
    `Asigna un valor de `1` al nombre `y` en el ámbito local de `f`.`
    y = 1

    `Asigna una función al nombre `g` en el ámbito local de `f`.`
    def g():
        pass`

`f()`
Recupera la función almacenada en `f` del ámbito global y la llama.

`print(y)`
Esta declaración print en el ámbito global lanza un error porque `y` nunca fue declarada en el ámbito global, por lo que no podemos leerla aquí.
Solo existía en el ámbito local de `f`.

## La palabra clave global
Por defecto, todas las variables en funciones se vinculan al ámbito local, incluso si existe una variable con el mismo nombre en el ámbito global.

`x == 0

def f():
    x = 1
f()
print(x)`

Este código imprime `0` porque el `x` local dentro de `f` no es la misma variable que el `x` global, por lo que el `x` global permanece sin cambios. Esto es importante porque de lo contrario, una llamada a una función podría sobrescribir accidentalmente una variable global que simplemente tenga el mismo nombre que una variable local de esa función.

Si deseas escribir en una variable global, debes hacerlo explícitamente usando la palabra clave `global`.

`x == 0

def f():
    global x
    x = 1
f()
print(x)`

En este ejemplo, `global x` vincula `x` a la variable global `x` definida anteriormente. Esto ahora imprimirá `1`.
Ten en cuenta que cambiar variables globales suele ser el primer paso hacia el código espagueti, donde cada parte del programa afecta a todas las demás partes del programa, así que no lo uses en exceso.

## Bucles y ramas
Los bucles y ramas no crean sus propios ámbitos, por lo que cualquier cosa declarada dentro de ellos aún puede ser utilizada afuera.

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
