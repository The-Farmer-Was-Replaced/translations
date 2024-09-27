# External Editor
El editor de texto del juego suele ser suficiente para jugar, pero por supuesto no puede competir con editores de texto más sofisticados como Visual Studio Code.

El juego guarda todos los archivos de código como archivos .py, por lo que puedes editarlos con editores de Python.
Ten en cuenta que esto es solo por conveniencia. El lenguaje del juego no es realmente Python, pero es lo suficientemente parecido como para que IntelliSense de Python funcione decentemente en él.
Puedes encontrar los archivos en la [carpeta de guardado](persistent_data_path/Saves).

Cada guardado también contiene un archivo `__builtins__.py`, que contiene definiciones de Python integradas que coinciden con las integradas del juego para habilitar IntelliSense.
El juego ignorará las declaraciones de importación de Python, por lo que puedes agregarlas para ayudar a tu editor externo a reconocer las definiciones de funciones de otros archivos.

Para ver los cambios externos en el juego sin tener que recargar la partida, debes habilitar la opción "File Watcher". Si creas o eliminas archivos externamente, aún necesitarás recargar la partida para verlos.

## Usando VS Code
Visual Studio Code es el editor de código recomendado para usar con The Farmer Was Replaced.

Puedes instalarlo [aquí](https://code.visualstudio.com/download).

Después de descargarlo, instala la extensión de Python en VS Code.

Una vez que tengas eso, abre la [carpeta](persistent_data_path/Saves) que contiene tus archivos `.py` en VS Code. Asegúrate de abrir toda la carpeta, no solo los archivos individuales, de lo contrario el archivo `__builtins__.py` no funcionará.

La extensión de Python no importa automáticamente funciones de otros archivos como lo hace el juego. Así que para evitar obtener advertencias de "no definido" en el editor al llamar funciones de otros archivos, necesitarás agregar la línea

`from filename import *`

en la parte superior de cada archivo que llame a las funciones de ese archivo (reemplaza `filename` con el nombre del archivo).
El juego ignorará estas declaraciones.

En el juego, asegúrate de tener activada la opción "File Watcher". Ahora, cada vez que guardes en VS Code, los cambios se mostrarán automáticamente en el juego.

¡Eso es todo! ¡Ahora puedes escribir tu código en un editor de código profesional!
