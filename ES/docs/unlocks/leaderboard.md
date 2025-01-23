# Tabla de Clasificación
Si has llegado hasta aquí, has superado muchos desafíos. Pero, ¿los has resuelto de manera eficiente?
Puedes competir con otros jugadores en varias tablas de clasificación para encontrar los métodos de cultivo más eficientes.

Puedes iniciar una partida para la tabla de clasificación llamando a `leaderboard_run(leaderboard, filename, speedup)`.
Esto inicia una [simulación](docs/unlocks/simulation.md) similar a `simulate()`, pero con condiciones iniciales fijas. Cada categoría de la tabla de clasificación tiene diferentes condiciones de inicio y éxito.

La partida tiene éxito si la condición de éxito es `True` cuando termina la simulación.
Si la partida es exitosa, tu tiempo se añadirá a la tabla de clasificación.

Para reducir la varianza, todas las partidas deben ejecutarse durante al menos 2 horas (Puedes acelerarlo, así que no tardará tanto). Si una partida se completa antes, se repetirá hasta alcanzar un tiempo total de 2 horas. El promedio de todas las partidas se subirá como tu puntuación.

## Reinicio más Rápido
El reinicio más rápido es la categoría más prestigiosa. Automatiza completamente el juego desde una única parcela de cultivo hasta desbloquear nuevamente las tablas de clasificación.

No necesitas desbloquear todo, solo intenta desbloquear `Unlocks.Leaderboard` lo más rápido posible.

Recuerda que puedes usar `num_unlocked(unlock) > 0` para verificar si algo está desbloqueado y puedes usar `get_cost()` en los desbloqueos para ver qué cuestan, así podrás cultivar automáticamente los elementos correctos.

Llamada a la Función:
`leaderboard_run(Leaderboards.Fastest_Reset, filename, speedup)`

Simulación Equivalente:
`unlocks = {}
items = {}
globals = {}
#un valor de semilla negativo significa una semilla aleatoria
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Condición de Éxito:
`num_unlocked(Unlocks.Leaderboard) > 0`

## Laberinto
Comienza con todo desbloqueado y cultiva `300000` de oro lo más rápido posible. Esta es exactamente la cantidad de oro que ganarás resolviendo un laberinto `300` veces.

Llamada a la Función:
`leaderboard_run(Leaderboards.Maze, filename, speedup)`

Simulación Equivalente:
`unlocks = Unlocks
items = {Items.Weird_Substance : 1000000, Items.Power: 1000000}
globals = {}
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Condición de Éxito:
`num_items(Items.Gold) >= 300000`

## Dinosaurio
Comienza con todo desbloqueado y cultiva `98010` huesos lo más rápido posible. Este es exactamente el número de huesos que obtendrás si llenas un área de 10x10 con tu cola.

Llamada a la Función:
`leaderboard_run(Leaderboards.Dinosaur, filename, speedup)`

Simulación Equivalente:
`unlocks = Unlocks
items = {Items.Pumpkin : 1000000, Items.Power: 1000000}
globals = {}
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Condición de Éxito:
`num_items(Items.Bone) >= 98010`

## Otras Tablas de Clasificación de Recursos
Cada planta tiene su propia tabla de clasificación para cultivar ese recurso en particular lo más rápido posible. Comienzas con todos los desbloqueos, los recursos que necesitas para cultivar la planta y mucha energía. El objetivo es cultivar `100000` del recurso producido por la planta.

Llamadas a Funciones:
`leaderboard_run(Leaderboards.Cactus, filename, speedup)`
`leaderboard_run(Leaderboards.Sunflowers, filename, speedup)`
`leaderboard_run(Leaderboards.Pumpkins, filename, speedup)`
`leaderboard_run(Leaderboards.Wood, filename, speedup)`
`leaderboard_run(Leaderboards.Carrots, filename, speedup)`
`leaderboard_run(Leaderboards.Hay, filename, speedup)`
`leaderboard_run(Leaderboards.Polyculture, filename, speedup)`

Condición de Éxito:
`num_items(resource) >= 100000`

`Leaderboards.Polyculture` requiere cultivar `100000` de los tres recursos de policultivo.
