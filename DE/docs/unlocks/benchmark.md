# Benchmark
Es gibt zwei nützliche Funktionen, um zu messen, wie lange Dinge dauern:

`get_time()` gibt die Zeit in Sekunden seit dem Start des Spiels zurück.

`get_op_count()` gibt die Anzahl der seit Beginn der Ausführung durchgeführten Operationen zurück.

Die meisten Aktionen benötigen eine konstante Anzahl von Operationen, und solange der Geschwindigkeitsfaktor gleich bleibt, ist die Zeit pro Operation ebenfalls konstant.

Aktionen, die die Drohne nicht beeinflussen, wie das Lesen von Variablen und das Aufrufen von Funktionen, zählen alle als `1` Operation. (Das Aufrufen einer Funktion besteht normalerweise darin, die Funktion aus einer Variablen zu lesen und sie dann aufzurufen, also sind es `2` Operationen)

Drohnaktionen wie Pflanzen, Ernten oder Bewegen zählen als `200` Operationen.

Beachten Sie, dass die Leistung in der realen Welt viel komplexer ist als dies. Konsistente Operationszählungen wie diese sind eine Vereinfachung, die für dieses Spiel gemacht wurde.
