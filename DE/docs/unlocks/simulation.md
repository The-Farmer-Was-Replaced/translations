# Simulation

Simulationen ermöglichen es dir, Code schnell zu testen, ohne den Zustand der echten Farm zu verändern.
Der Anfangszustand der Simulation kann frei gewählt werden, und wenn die Simulation endet, wird die echte Farm genau in dem Zustand sein, in dem sie vor dem Start der Simulation war.

Die Funktion `simulate()` wird verwendet, um eine Simulation zu starten.

Die Datei, in der die Ausführung beginnen soll
`filename = "f1"`

Starte mit allen Freischaltungen und vollständigen Verbesserungen
`sim_unlocks = Unlocks`

Starte mit 10000 Karotten und 50 Heu
`sim_items = {Items.Carrot : 10000, Items.Hay : 50}`

Starte mit einer globalen Variable "a" mit dem Wert 13
`sim_globals = {"a" : 13}`

Verwende einen festen Zufallsseed
`seed = 0`

Beschleunige die Simulation um den Faktor 64
`speedup = 64`

Starte die Simulation
`run_time = simulate(filename, sim_unlocks, sim_items, sim_globals, seed, speedup)`

Die Funktion `simulate()` gibt die Zeit in Sekunden zurück, die für die Simulation der angegebenen Startdatei benötigt wurde.

### Dateiname
Das erste Argument der Simulate-Funktion ist der Dateiname. Dies ist der Name, der oben im Code-Fenster angezeigt wird. Die Simulation führt die angegebene Datei aus, als hätten Sie auf die Ausführen-Schaltfläche geklickt.

### Start-Freischaltungen
Alle Programmierfunktionen wie Schleifen, if-Anweisungen, Listen, Dictionaries,... bleiben immer freigeschaltet.

Das zweite Argument ermöglicht es dir festzulegen, mit welchen Freischaltungen/Verbesserungen die Simulation zusätzlich zu den Programmierfunktionen starten soll. Dies sollte eine Sequenz von Freischaltungen sein. Die Simulation startet mit allen Freischaltungen in der Sequenz auf ihrer maximalen Stufe.

Wenn du eine andere als die maximale Freischaltungsstufe festlegen möchtest, kannst du ein Dictionary übergeben, das die Freischaltungen den Freischaltungsstufen zuordnet. In diesem Fall entsprechen negative Werte der maximalen Freischaltungsstufe.

### Start-Items
Das dritte Argument ermöglicht es dir, ein Dictionary zu übergeben, das Items Zahlen zuordnet. Es legt fest, mit welchen Items die Simulation starten soll.

### Start-Globale-Variablen
Da die Simulation eine völlig neue Programmausführung startet, kannst du nicht auf Variablen aus dem Programm zugreifen, das die Simulation startet.
Es ist jedoch möglich, Werte an die Simulation über das vierte Argument zu übergeben. Dies ist ein Dict, das Variablennamen in Form von Strings Werten zuordnet. Diese Variablen werden dann dem globalen Gültigkeitsbereich der Ausführung innerhalb der Simulation hinzugefügt.

Beachte, dass alle Werte kopiert werden, sodass deren Änderung innerhalb der Simulation keine Auswirkungen auf die ursprünglichen Werte außerhalb der Simulation hat. Es ist nicht möglich, andere Werte aus der Simulation zurückzugeben als die Zeit, die für die Ausführung benötigt wurde.

### Zufallsseed
Das fünfte Argument ermöglicht es dir, den in der Simulation verwendeten Zufallsseed festzulegen. Dies muss eine positive Ganzzahl sein. Negative Werte führen dazu, dass ein zufälliger Seed verwendet wird.

Der Zufallsseed beeinflusst alles, von Pflanzenwachstumszeiten über Labyrinth-Layouts bis hin zu Wasserzerfallszeiten. Wenn du dieselbe Simulation mehrmals mit demselben Zufallsseed und denselben Startbedingungen startest, sollte das Ergebnis immer gleich sein.

### Beschleunigung
Das sechste Argument ist die Startbeschleunigung der Simulation. Dies ermöglicht es dir, Dinge schnell zu testen. Wenn das Spiel mit der eingestellten Geschwindigkeit nicht mithalten kann, wird es automatisch verlangsamt.

Die Beschleunigung hat keinerlei Einfluss auf das Ergebnis der Simulation. Sie existiert nur, um die Wartezeit zu reduzieren.
