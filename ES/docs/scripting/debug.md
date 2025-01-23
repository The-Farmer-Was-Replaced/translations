# Depuración

A veces tu código simplemente no funciona y necesitas descubrir por qué. Hay un par de herramientas que te ayudarán a hacerlo.

La primera es ejecutar el programa paso a paso.
Puedes entrar en modo paso a paso con el botón al lado del botón Ejecutar o estableciendo un punto de interrupción.

Los puntos de interrupción se pueden agregar haciendo clic en el panel de puntos de interrupción a la izquierda del código.
![](Breakpoints227)
Cuando la ejecución alcanza la línea donde está el punto de interrupción, cambiará automáticamente al modo paso a paso.

Cuando pasas el cursor sobre una variable, se muestra su valor actual.

La función `print()` también puede ser muy útil. Imprimirá cualquier valor pasado directamente al aire.

Ejemplos:

`print(0.24) #imprime "0.24"

print(can_harvest()) #imprime "True" o "False"

print(get_pos_x(), get_pos_y()) #imprime la posición actual`

La función print imprime el valor directamente al aire y en la página de [Salida](docs/output.md).

Imprimir al aire puede ser un poco lento si quieres imprimir muchos valores.
En este caso, puedes usar la función `quick_print()` que solo imprime en la ventana de salida.

La ventana de salida también registra advertencias y errores, por lo que puede ser útil verificar eso si algo no funciona como se espera.

Cuando la ejecución se detiene, la salida también se escribe en el archivo output.txt en la carpeta del juego. Puedes encontrar la carpeta del juego seleccionando Menú -> Cargar -> Abrir Carpeta.
