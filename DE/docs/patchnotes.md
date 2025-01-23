
# Patchnotizen

### Breaking Changes:
Du musst diese in deinem Code ändern.

Funktionen, die in anderen Dateien (Fenstern im Spiel) definiert sind, werden nicht mehr implizit importiert. Du musst jetzt explizite Importanweisungen wie in Python freischalten und verwenden (siehe Import freischalten).

### Bereits verpasste Breaking Changes aus älteren Patches:
- `Items.Bones` wurde in `Items.Bone` umbenannt, sodass alle Items im Singular sind.
- `Entities.Carrots` wurde in `Entities.Carrot` umbenannt, sodass alle Entities im Singular sind.
- `Grounds.Turf` wurde in `Grounds.Grassland` umbenannt, um das Verständnis zu erleichtern.
- `Items.Water_Tank` wurde in `Items.Water` umbenannt, da die Tanknachfüllfunktion entfernt wurde.
- `Unlocks.Benchmark` wurde durch `Unlocks.Timing` ersetzt.
- `get_op_count()` wurde in `get_tick_count()` umbenannt.
- `set_farm_size()` wurde in `set_world_size()` umbenannt, um mit `get_world_size()` konsistent zu sein.
- `get_companion()` gibt jetzt ein Tupel der Form (entity, (x, y)) statt einer Liste zurück.
- `trade()` wurde aus dem Spiel entfernt.

### Globale Variablen:
- Scopes und globale Variablen wurden geändert, um wie in Python zu funktionieren. Das bedeutet, du kannst jetzt das `global`-Schlüsselwort verwenden, um im globalen Scope zu schreiben.
- Es gibt jetzt einen Fehler, wenn eine lokale Variable verwendet wird, bevor sie lokal zugewiesen wurde, selbst wenn es eine globale Variable mit demselben Namen gibt.
- Die Fehlermeldungen zum Überschreiben wurden entfernt.

### Imports:
Das alte Importsystem importierte automatisch alle Funktionen aus allen Dateien. Dies hatte den großen Nachteil, dass globale Variablen aus anderen Dateien nicht importiert werden konnten und daher nicht zugänglich waren.
Das neue Importsystem ist eine leicht vereinfachte Version davon, wie Importe in Python funktionieren. Du kannst ein Modul mit der Syntax `import file` oder `from file import *` importieren.

### Andere Änderungen:
- Hinzugefügt: `str()` Funktion.
- Hinzugefügt: Destrukturierungsunterstützung in for-Schleifen.
- Verschiedene Dokumentationsänderungen.
- Fehlerbehebungen beim Übergeben von Funktionen in Simulationen.
- Fehlerbehebungen bei der Verwendung von `in` und `not in` mit Funktionen.
- Fehlerbehebungen bei der `set`-Funktion, die Listen als Schlüssel zulässt.
