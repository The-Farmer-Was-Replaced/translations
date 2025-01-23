
# Notas del Parche

### Cambios Rompedores:
Tendrás que cambiar estos en tu código.

Las funciones definidas en otros archivos (ventanas en el juego) ya no se importan implícitamente. Ahora debes desbloquear y usar declaraciones de importación explícitas como en Python (ver desbloqueo de importación).

### Cambios Rompedores de Parches Anteriores que Podrías Haber Perdid:
- `Items.Bones` ha sido renombrado a `Items.Bone` para que todos los ítems estén en singular.
- `Entities.Carrots` ha sido renombrado a `Entities.Carrot` para que todas las entidades estén en singular.
- `Grounds.Turf` ha sido renombrado a `Grounds.Grassland` para facilitar la comprensión.
- `Items.Water_Tank` ha sido renombrado a `Items.Water` porque se eliminó la función de recarga del tanque.
- `Unlocks.Benchmark` ha sido reemplazado por `Unlocks.Timing`.
- `get_op_count()` ha sido renombrado a `get_tick_count()`.
- `set_farm_size()` ha sido renombrado a `set_world_size()` para ser consistente con `get_world_size()`.
- `get_companion()` ahora devuelve una tupla de la forma (entity, (x, y)) en lugar de una lista.
- `trade()` ha sido eliminado del juego.

### Variables Globales:
- Los Scopes y variables globales han sido cambiados para funcionar como en Python. Esto significa que ahora puedes usar la palabra clave `global` para escribir en el scope global.
- Ahora hay un error al usar una variable local antes de que haya sido asignada localmente, incluso si hay una variable global con el mismo nombre.
- Los mensajes de error de sombreado han sido eliminados.

### Importaciones:
El antiguo sistema de importación importaba automáticamente todas las funciones de todos los archivos. Esto tenía la gran desventaja de que las variables globales de otros archivos no podían ser importadas y, por lo tanto, no eran accesibles.
El nuevo sistema de importación es una versión ligeramente simplificada de cómo funcionan las importaciones en Python. Puedes importar un módulo usando la sintaxis `import file` o `from file import *`.

### Otros Cambios:
- Añadida la función `str()`.
- Añadido soporte de desestructuración en bucles for.
- Varios cambios en la documentación.
- Correcciones al pasar funciones en simulaciones.
- Correcciones al usar `in` y `not in` con funciones.
- Corrección de la función set que permitía listas como claves.
