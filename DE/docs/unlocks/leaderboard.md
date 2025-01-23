# Bestenliste
Wenn du es bis hierher geschafft hast, hast du viele Herausforderungen gemeistert. Aber hast du sie auch effizient gelöst?
Du kannst dich mit anderen Spielern in verschiedenen Bestenlisten für die effizientesten Farming-Methoden messen.

Du kannst einen Bestenlisten-Durchlauf mit `leaderboard_run(leaderboard, filename, speedup)` starten.
Dies startet eine [Simulation](docs/unlocks/simulation.md) ähnlich wie `simulate()`, nur dass die Startbedingungen fest vorgegeben sind. Jede Bestenlisten-Kategorie hat unterschiedliche Start- und Erfolgsbedingungen.

Der Bestenlisten-Durchlauf ist erfolgreich, wenn die Erfolgsbedingung am Ende der Simulation `True` ist.
Wenn der Durchlauf erfolgreich ist, wird deine Zeit zur Bestenliste hinzugefügt.

Um Schwankungen zu reduzieren, müssen alle Durchläufe mindestens 2 Stunden laufen (Du kannst sie beschleunigen, sodass es nicht so lange dauert). Wenn ein Durchlauf früher beendet wird, wird er wiederholt, bis eine Gesamtzeit von 2 Stunden erreicht ist. Der Durchschnitt aller Durchläufe wird dann als dein Ergebnis hochgeladen.

## Schnellster Neustart
Der schnellste Neustart ist die prestigeträchtigste Kategorie. Automatisiere das Spiel komplett von einem einzigen Farmfeld bis zum erneuten Freischalten der Bestenlisten.

Du musst nicht alles freischalten, versuche einfach `Unlocks.Leaderboard` so schnell wie möglich freizuschalten.

Denk daran, dass du mit `num_unlocked(unlock) > 0` prüfen kannst, ob etwas freigeschaltet ist, und du mit `get_cost()` bei Freischaltungen sehen kannst, was sie kosten, damit du automatisch die richtigen Items farmen kannst.

Funktionsaufruf:
`leaderboard_run(Leaderboards.Fastest_Reset, filename, speedup)`

Äquivalente Simulation:
`unlocks = {}
items = {}
globals = {}
#ein negativer Seed-Wert bedeutet einen zufälligen Seed
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Erfolgsbedingung:
`num_unlocked(Unlocks.Leaderboard) > 0`

## Labyrinth
Starte mit allen Freischaltungen und farme so schnell wie möglich `300000` Gold. Dies ist genau die Menge Gold, die du durch 300-maliges Lösen eines Labyrinths verdienst.

Funktionsaufruf:
`leaderboard_run(Leaderboards.Maze, filename, speedup)`

Äquivalente Simulation:
`unlocks = Unlocks
items = {Items.Weird_Substance : 1000000, Items.Power: 1000000}
globals = {}
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Erfolgsbedingung:
`num_items(Items.Gold) >= 300000`

## Dinosaurier
Starte mit allen Freischaltungen und farme so schnell wie möglich `98010` Knochen. Dies ist genau die Anzahl an Knochen, die du erhältst, wenn du einen 10x10 Bereich mit deinem Schwanz füllst.

Funktionsaufruf:
`leaderboard_run(Leaderboards.Dinosaur, filename, speedup)`

Äquivalente Simulation:
`unlocks = Unlocks
items = {Items.Pumpkin : 1000000, Items.Power: 1000000}
globals = {}
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Erfolgsbedingung:
`num_items(Items.Bone) >= 98010`

## Andere Ressourcen-Bestenlisten
Jede Pflanze hat ihre eigene Bestenliste für das schnellstmögliche Farmen dieser bestimmten Pflanze. Du startest mit allen Freischaltungen, den Ressourcen, die du zum Anbau der Pflanze brauchst, und viel Energie. Das Ziel ist es, `100000` der von der Pflanze produzierten Ressource zu farmen.

Funktionsaufrufe:
`leaderboard_run(Leaderboards.Cactus, filename, speedup)`
`leaderboard_run(Leaderboards.Sunflowers, filename, speedup)`
`leaderboard_run(Leaderboards.Pumpkins, filename, speedup)`
`leaderboard_run(Leaderboards.Wood, filename, speedup)`
`leaderboard_run(Leaderboards.Carrots, filename, speedup)`
`leaderboard_run(Leaderboards.Hay, filename, speedup)`
`leaderboard_run(Leaderboards.Polyculture, filename, speedup)`

Erfolgsbedingung:
`num_items(resource) >= 100000`

`Leaderboards.Polyculture` erfordert das Farmen von `100000` aller drei Polykultur-Ressourcen.
