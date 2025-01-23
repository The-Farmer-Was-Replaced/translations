# Dinosaurios
Los dinosaurios son criaturas antiguas y majestuosas que se pueden criar para obtener huesos antiguos.

Desafortunadamente, los dinosaurios se extinguieron hace mucho tiempo, por lo que lo mejor que podemos hacer ahora es disfrazarnos de uno.
Para este propósito, has recibido el nuevo sombrero de dinosaurio.

El sombrero se puede equipar con
`change_hat(Hats.Dinosaur_Hat)`

Desafortunadamente, no se ve igual que en el anuncio...

Si equipas el sombrero de dinosaurio y tienes suficientes calabazas, se comprará automáticamente una [manzana](objects/apple) y se colocará debajo del dron.
Cada vez que te alejas de una manzana, la cola del sombrero de dinosaurio crecerá un bloque y, si tienes suficientes objetos, se comprará y colocará una nueva manzana en un lugar aleatorio.
La manzana no puede aparecer si ya hay algo plantado donde quiere estar.

La cola del dinosaurio será arrastrada detrás del dron llenando los bloques anteriores por los que el dron se ha movido. Si un dron intenta moverse sobre la cola, `move()` fallará y devolverá `False`.
El último segmento de la cola se moverá para despejar el camino durante el movimiento, así que puedes moverte sobre él. Sin embargo, si la serpiente llena todo el campo, ya no podrás moverte. Así que puedes comprobar si la serpiente está totalmente crecida verificando si no puedes moverte.

Usar `measure()` en una manzana devolverá la posición de la siguiente manzana como una tupla.

`next_x, next_y = measure()`

Cuando el sombrero se desequipa nuevamente al equipar otro sombrero, la cola será cosechada.
Recibirás huesos iguales al cuadrado de la longitud de la cola. Así que para una cola de longitud `n` recibirás `n**2` `Items.Bone`.
Por ejemplo:
longitud 1 => 1 hueso
longitud 2 => 4 huesos
longitud 3 => 9 huesos
longitud 4 => 16 huesos
longitud 16 => 256 huesos
longitud 100 => 10000 huesos

El Sombrero de Dinosaurio es muy pesado, por lo que si lo equipas, `move()` tardará 800 ticks en lugar de 200. Sin embargo, cada vez que recoges una manzana, el número de ticks usados por `move()` se reduce en un 3% (redondeado hacia abajo), porque una cola más larga puede ayudarte a moverte.

El siguiente bucle imprime el número de ticks usados por `move()` después de cualquier cantidad de manzanas:

`ticks = 800
for i in range(100):
    print("ticks after ", i, " apples: ", ticks)
    ticks -= ticks * 0.03 // 1`

<spoiler=mostrar pista 1>Si sigues moviéndote por el mismo camino que cubre todo el campo, puedes obtener fácilmente una serpiente de campo completa cada vez, porque cubrirás cada lugar libre antes de volver a donde está tu cola. No es muy eficiente, pero funciona.</spoiler>
