
# Import
Poner todo tu código en un solo archivo se vuelve inmanejable rápidamente.
Las sentencias `import` te permiten importar funciones y variables globales desde otro archivo.

`import filename`

Esta es la forma más simple de la instrucción de importación. Te dará acceso a todo lo que se haya definido en el archivo llamado `filename`. Cada ventana en el juego es un archivo, y el nombre del archivo es el que se muestra en la parte superior de la ventana.

Aquí hay un ejemplo con dos archivos:
Archivo llamado helper:
`def say_hello():
    print("hello from helper")`

Algún otro archivo:
`import helper
helper.say_hello()`

Aquí `import helper` ejecuta el archivo helper y te da acceso a todas sus variables globales.
Luego puedes acceder a las variables y funciones dentro del módulo importado usando el operador `.`.
En este ejemplo, `helper.say_hello()` llama a la función `say_hello()` dentro de helper.

También puedes mover las variables globales del módulo importado al scope actual donde se ejecuta la sentencia de importación usando la sintaxis `from`.

`from helper import *`
Importa todas las variables globales de helper.

o

`from helper import say_hello`
Importa únicamente las variables globales especificadas de helper.

Esto también importa el archivo helper, pero en lugar de acceder a él a través de una variable llamada `helper`, “desempaqueta” las variables globales de `helper` y las asigna directamente en el scope local.

`from helper import say_hello
say_hello()`

Esta forma de importación generalmente no se recomienda porque podrías sobrescribir variables en el archivo importado debido a colisiones de nombres.

## Lo que realmente hace
La primera vez que importas un archivo, se ejecuta todo el contenido del archivo y luego obtienes acceso a todas las variables definidas durante la ejecución.
Si importas el mismo archivo de nuevo, simplemente devolverá las variables globales en caché de la primera vez.

Esto significa que las sentencias de importación pueden tener efectos secundarios. Si importas un archivo que llama a `harvest()`, realmente se realizará la cosecha durante la importación. Pero cuando lo importas de nuevo, no se ejecutará otra vez porque el archivo solo se ejecuta una vez.

Hay una forma de evitar estos efectos secundarios usando la variable `__name__`. Esta variable se establece automáticamente en `"__main__"` cuando un archivo se ejecuta directamente, y en el nombre del archivo cuando se ejecuta a través de `import`.
Se considera una buena práctica poner cualquier código que no quieras que se ejecute al importar el archivo dentro de un bloque `if __name__ == "__main__":`.

Una estructura de archivo común en Python consiste en poner el código que debe ejecutarse cuando el archivo se ejecute directamente dentro de una función `main()`. De esta manera tienes una clara distinción entre las variables de script locales (definidas dentro de `main()`) y las variables globales que se pueden importar (definidas fuera de `main()`).

`a_global = "global value"

def main():
    a_local = "local value"
    //do things

if __name__ == "__main__":
    main()`
