# Loading Backups
Desafortunadamente, a veces un archivo de guardado se corrompe o pierdes algunos archivos de código. Si esto te sucede, puedes intentar cargar una copia de seguridad. Si ocurre regularmente, intenta desactivar Steam Cloud.

Se hace una copia de seguridad cada vez que se guarda el juego, y se mantiene un pequeño número de copias de seguridad en caso de que necesites restaurar algo.
Estas copias de seguridad se pueden encontrar en el [directorio de copias de seguridad](persistent_data_path/Backup). Son copias de los guardados en el [directorio de guardados](persistent_data_path/Saves).
La forma más fácil de cargar una copia de seguridad es copiar la carpeta de la copia de seguridad específica que deseas cargar al directorio de guardados.

Un guardado es una carpeta con un archivo `save.json` y un montón de archivos `.py`.
Si solo perdiste algunos archivos de código, o los archivos de código aún están allí pero el archivo `save.json` está corrupto, también puedes reemplazar solo las partes corruptas con los archivos correspondientes de la copia de seguridad.
