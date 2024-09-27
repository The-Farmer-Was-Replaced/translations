# Leaderboard
El desafío definitivo de la agricultura automatizada es jugar a través del juego automáticamente lo más rápido posible.

Llamar a `timed_reset()` guardará el juego, restablecerá todos los desbloqueos y mejoras que no estén relacionados con la programación, y comenzará el temporizador del tablero de líderes.

Conservas todas las características del lenguaje como `while, if, for`, variables, operadores y sensores.
También conservas los costos y desbloqueos automáticos para que puedas automatizar completamente el juego.

Si la ejecución del programa se detiene, la carrera se aborta.
La carrera termina cuando la ejecución llama a `timed_reset()` nuevamente.
No necesitas tener todo desbloqueado, solo intenta desbloquear `Unlocks.Leaderboard` y llama a `timed_reset()` lo más rápido posible.

Después de que la carrera termine o se aborte, se cargará la partida guardada antes de la carrera.

Mientras el temporizador está en funcionamiento, tienes la opción de acelerar el tiempo para no tener que esperar tanto.

Recuerda que puedes usar `num_unlocked(unlock) > 0` para verificar si algo está desbloqueado y puedes usar `get_cost()` en tus desbloqueos para ver cuánto cuestan y así poder cultivar automáticamente los elementos correctos.
