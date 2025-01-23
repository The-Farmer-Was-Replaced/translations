# Timing
Wenn Sie Ihre Methoden wirklich optimieren möchten, müssen Sie verstehen, wie die Zeit in diesem Spiel gemessen wird. Dieser Unlock erklärt genau das.

## Neue Funktionen
Es gibt zwei nützliche Funktionen, um zu messen, wie lange Dinge dauern:

`get_time()` gibt die Zeit in Sekunden seit dem Start des Spiels zurück.

`get_tick_count()` gibt die Anzahl der ausgeführten Ticks seit dem Start der Ausführung zurück.

Diese beiden Funktionen sowie `quick_print()` sind völlig kostenlos. Sogar der Funktionsaufruf ist bei ihnen kostenlos.

## Laufzeitdetails

### Haftungsausschluss
So funktioniert Leistung nicht in der realen Welt. Dies sind nur Regeln, die für dieses Spiel erfunden wurden.
Dies ist wahrscheinlich nur wichtig, wenn Sie Ihren Code hyper-optimieren möchten.

Die Grundeinheit der Zeit für die Codeausführung wird "Tick" genannt. Ohne Geschwindigkeitsverbesserungen und Energie läuft die Ausführung mit einer Rate von `400` Ticks pro Sekunde.

Im Allgemeinen benötigen Operationen, die zwei Werte kombinieren, wie `+, -, *, /, //, %, and, or, ...` einen Tick.
Einzelwert `-` und `not` sind kostenlos.
Eine `if`-Verzweigung benötigt ebenfalls einen Tick (zusätzlich zur Zeit für die Auswertung des Bedingungsausdrucks).
Funktionsaufrufe und Variablen lesen und schreiben sind kostenlos, aber Funktionsdefinitionen benötigen 1 Tick.
`import`-Anweisungen sind kostenlos.
Der Zugriff auf ein importiertes Modul mit dem `.`-Operator ist kostenlos.
Wenn eine Funktion oder ein Modul über Argumente oder Variablenzuweisungen übergeben wurde, kostet die Verwendung 1 Tick statt 0.
`for` und `while`-Schleifen benötigen einen Tick zum Starten, aber die Iterationen sind kostenlos (ohne die Zeit für die Auswertung der Bedingungs-/Sequenzausdrücke).
`return`, `break` und `continue` sind alle kostenlos.
`pass` benötigt einen Tick und kann daher für präzise Verzögerungen verwendet werden.
Die Indizierung in eine Datenstruktur benötigt einen Tick für den Indexoperator und bei einem Dictionary oder Set zusätzliche Ticks abhängig von der Größe des Schlüssels.

Die Anzahl der Ticks, die eingebaute Funktionen zur Ausführung benötigen, ist in der Dokumentation jeder Funktion individuell dokumentiert.
