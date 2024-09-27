# Debug
A veces tu código simplemente no funciona y necesitas averiguar por qué. Hay un par de herramientas que te pueden ayudar con eso.

La primera es ejecutar el programa paso a paso.
Puedes entrar en modo paso a paso con el botón al lado del botón Ejecutar o configurando un punto de interrupción.

Los puntos de interrupción se pueden agregar haciendo clic en el panel de puntos de interrupción a la izquierda del código.
![](Breakpoints227)
Cuando la ejecución llega a la línea donde está el punto de interrupción, cambiará automáticamente al modo paso a paso.

Cuando pasas el cursor sobre una variable, se muestra su valor actual.

La función `print()` también puede ser muy útil. Imprimirá cualquier valor que se le pase directamente en el aire.

Ejemplos:

`print(0.24) #imprime "0.24"

print(can_harvest()) #imprime "True" o "False"

print(get_pos_x(), get_pos_y()) #imprime la posición actual`

La función print imprime el valor directamente en el aire y en la página de [Salida](docs/output.md).

Imprimir en el aire a veces puede ser un poco lento si quieres imprimir muchos valores.
En este caso, puedes usar la función `quick_print()` que imprime solo en la ventana de salida.

La ventana de salida también registra advertencias y errores, por lo que si algo no funciona como se espera, puede ser útil verificar eso.

Cuando la ejecución se detiene, la salida también se escribe en el archivo output.txt en la carpeta del juego. Puedes encontrar la carpeta del juego seleccionando Menú -> Cargar -> Abrir Carpeta.
