
# Importar
Colocar todo tu código en un solo archivo se vuelve rápidamente inmanejable.
Las instrucciones `import` te permiten importar funciones y variables globales de otro archivo.

`import nombre_archivo`

Esta es la forma más simple de una declaración de importación. Te dará acceso a todo lo definido en el archivo llamado `nombre_archivo`. Cada ventana en el juego es un archivo, y el nombre del archivo es el nombre mostrado en la parte superior de la ventana.

Aquí hay un ejemplo con dos archivos:
Archivo llamado helper:
`x = 0

def say_hello():
    print("hola desde helper")`

Otro archivo:
`import helper
helper.say_hello()
helper.x += 1`

Aquí, `import helper` ejecuta el archivo llamado `helper` y te da acceso a todos sus globales.
Luego puedes acceder a variables y funciones dentro del módulo importado usando el operador `.`.
Entonces en este ejemplo, `helper.say_hello()` llama a `say_hello()` dentro de helper y la última línea incrementa la variable global x.

También puedes mover los globales del módulo importado al alcance actual donde se ejecuta la declaración de importación usando la sintaxis `from`.

`from helper import *`
Importa todos los globales de helper.

o

`from helper import say_hello`
Importa solo los globales especificados de helper.

Esto también importa el archivo helper, pero en lugar de acceder a él a través de una variable llamada `helper`, desempaqueta los globales de `helper` y los asigna directamente en el alcance local.

`from helper import say_hello
say_hello()`

Esta forma de importación generalmente no se recomienda porque no funciona bien cuando dos archivos se importan entre sí, y puedes sobrescribir accidentalmente variables en el archivo importador debido a colisiones de nombres.

# Cómo funciona realmente

## TLDR
Las importaciones pueden ser bastante poco intuitivas, pero la mayoría de los problemas se pueden evitar adhiriéndose a la sintaxis `import archivo` en lugar de `from archivo import`, y envolviendo todo lo que no es una definición global en
`if __name__ == "__main__":`

## Efectos Secundarios de las Importaciones
La primera vez que importas un archivo, ejecutará todo el archivo y luego te dará acceso a todas las variables que han sido definidas durante la ejecución.
Si importas el mismo archivo de nuevo, simplemente devolverá el módulo caché de la primera vez.

Esto significa que las declaraciones de importación pueden tener efectos secundarios. Si importas un archivo que llama a `harvest()`, en realidad cosechará durante la importación. Pero cuando lo importas de nuevo, no cosechará de nuevo porque el archivo solo se ejecuta una vez.

Existe una manera de evitar tales efectos secundarios usando la variable `__name__`. Esta es una variable que se establece automáticamente en `"__main__"` cuando un archivo se ejecuta directamente, y en el nombre del archivo cuando un archivo se ejecuta a través de `import`.
Se considera una buena práctica poner cualquier código que no quieras ejecutar cuando el archivo es importado dentro de un bloque `if __name__ == "__main__":`.

Una estructura de archivos común en Python es poner el código que debe ser ejecutado cuando el archivo es corrido en una función `main()`. De esta manera tienes una distinción clara entre variables locales (definidas dentro de `main()`) y variables globales que pueden ser importadas (definidas fuera de `main()`).

`a_global_variable = "global"

def main():
    a_local_variable = "local"
    // hacer cosas

if __name__ == "__main__":
    main()`

## Ciclos de Importación
¿Qué pasa si el archivo `a` importa al archivo `b` y el archivo `b` importa al archivo `a`?

archivo `a` :
`import b
x = 0`

archivo `b` :
`import a
def f():
    print(a.x)`

Esto funcionará bien. Supongamos que ninguno de los dos archivos está cargado aún, y alguien ejecuta `import a`.

- `a` se ejecuta hasta la línea `import b`.
- `b` se ejecuta hasta la línea `import a`.
- El módulo `a` ya existe, pero no contiene `x` porque solo ha ejecutado hasta la línea `import b`.
- `b` almacena una referencia al módulo `a` medio cargado en una variable llamada `a`.
- `b` ejecuta la declaración `def` y almacena la función `f()`.

Cuando alguien llama a `b.f()`, imprimirá correctamente `0` porque el módulo `a` al que `b` tiene una referencia ahora está completamente cargado.

Ahora considera el mismo código usando la sintaxis `from`.

archivo `a` :
`from b import *
x = 0`

archivo `b` :
`from a import *
def f():
    print(x)`

- `a` se ejecuta hasta la línea `from b import *`.
- `b` se ejecuta hasta la línea `from a import *`.
- El módulo `a` ya existe, pero aún no se ha ejecutado completamente.
- `b` desempaqueta todo lo que está actualmente en `a` en su propio espacio de nombres global. En este punto, `a` no contiene nada porque aún no ha llegado a la línea `x = 0`, así que no se importa nada.
- `b` ejecuta la declaración `def` y almacena la función `f()`.

Si alguien llama ahora a `b.f()`, obtendrá un error que `x` no existe en el espacio de nombres actual. Esto se debe a que esta vez `b` no tiene una referencia al `a` que aún se está cargando y no ve las definiciones que se agregaron después de la importación.

Si alguien ahora llama a `b.f()`, obtendrá un error de que `x` no existe en el alcance actual. Esto se debe a que esta vez `b` no tiene una referencia al `a` que aún se está cargando y no ve las definiciones que se agregaron después de la importación.
- `b` ejecuta la declaración `def` y almacena la función `f()`.
- `b` desempaqueta todo lo que actualmente está en `a` en su propio alcance global. En este punto, `a` no contiene nada porque aún no ha llegado a la línea `x = 0`, por lo que no se importa nada.
- `b` se ejecuta hasta la línea `from a import *`.
- El módulo `a` ya existe, pero aún no se ha ejecutado completamente.
    print(x)`

- `a` se ejecuta hasta la línea `from b import *`.

archivo `a`:
`from b import *
x = 0`

archivo `b`:
`from a import *
def f():

Cuando alguien llama a `b.f()`, imprimirá correctamente `0` porque el módulo `a` al que `b` tiene una referencia ya está completamente cargado.

Ahora considera el mismo código usando la sintaxis `from`.
- `b` ejecuta la declaración `def` y almacena la función `f()`.
- `b` almacena una referencia al módulo `a` medio cargado en una variable llamada `a`.
- `b` se ejecuta hasta la línea `import a`.
- El módulo `a` ya existe, pero no contiene `x` porque solo ha llegado a la línea `import b`.

Esto funcionará bien. Supongamos que ninguno de los dos archivos está cargado aún, y alguien ejecuta `import a`.

- `a` se ejecuta hasta la línea `import b`.
    print(a.x)`

archivo `a`:
`import b
x = 0`

archivo `b`:
`import a
def f():

## Ciclos de Importación
¿Qué pasa si el archivo `a` importa al archivo `b` y el archivo `b` importa al archivo `a`?
    a_local_variable = "local"
    // hacer cosas

if __name__ == "__main__":
    main()`

Una estructura de archivos común en Python es poner el código que debe ser ejecutado cuando el archivo es corrido en una función `main()`. De esta manera tienes una distinción clara entre variables locales (definidas dentro de `main()`) y variables globales que pueden ser importadas (definidas fuera de `main()`).

`a_global_variable = "global"

def main():
Se considera una buena práctica poner cualquier código que no quieras ejecutar cuando el archivo es importado dentro de un bloque `if __name__ == "__main__":`.

Existe una manera de evitar tales efectos secundarios usando la variable `__name__`. Esta es una variable que se establece automáticamente en `"__main__"` cuando un archivo se ejecuta directamente, y en el nombre del archivo cuando un archivo se ejecuta a través de `import`.

Esto significa que las declaraciones de importación pueden tener efectos secundarios. Si importas un archivo que llama a `harvest()`, en realidad cosechará durante la importación. Pero cuando lo importas de nuevo, no cosechará de nuevo porque el archivo solo se ejecuta una vez.
Si importas el mismo archivo de nuevo, simplemente devolverá el módulo caché de la primera vez.
La primera vez que importas un archivo, ejecutará todo el archivo y luego te dará acceso a todas las variables que han sido definidas durante la ejecución.

## Efectos Secundarios de Importar
Las importaciones pueden ser bastante poco intuitivas, pero la mayoría de los problemas se pueden evitar adhiriéndose a la sintaxis `import archivo` en lugar de `from archivo import`, y envolviendo todo lo que no es una definición global en
`if __name__ == "__main__":`

Esta forma de importación generalmente no se recomienda porque no funciona bien cuando dos archivos se importan entre sí, y puedes sobrescribir accidentalmente variables en el archivo que importa debido a colisiones de nombres.

# Cómo funciona realmente

## Resumen

`from helper import say_hello
say_hello()`

Esto también importa el archivo helper, pero en lugar de acceder a él a través de una variable llamada `helper`, desempaqueta los globales de `helper` y los asigna directamente en el alcance local.
Importa solo los globales especificados de helper.

`from helper import *`
Importa todos los globales de helper.

o

`from helper import say_hello`

También puedes mover los globales del módulo importado al alcance actual donde se ejecuta la declaración de importación usando la sintaxis `from`.
Entonces, en este ejemplo, `helper.say_hello()` llama a `say_hello()` dentro de helper y la última línea incrementa la variable global x.
Luego puedes acceder a variables y funciones dentro del módulo importado usando el operador `.`.

Aquí, `import helper` ejecuta el archivo llamado `helper` y te da acceso a todos sus globales.
    print("hola desde helper")`

Otro archivo:
`import helper
helper.say_hello()
helper.x += 1`

Aquí hay un ejemplo con dos archivos:
Archivo llamado helper:
`x = 0

def say_hello():

Esta es la forma más simple de una declaración de importación. Te dará acceso a todo lo definido en el archivo llamado `nombre_archivo`. Cada ventana en el juego es un archivo, y el nombre del archivo es el nombre mostrado en la parte superior de la ventana.
Las declaraciones `import` te permiten importar funciones y variables globales de otro archivo.

`import nombre_archivo`
# Importar
Colocar todo tu código en un solo archivo se vuelve rápidamente inmanejable.
