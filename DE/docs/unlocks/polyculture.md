# Polykultur
Vielleicht hast du schon bemerkt, dass manche Pflanzen mehr Ertrag bringen, wenn sie zusammen gepflanzt werden.
Gras, Büsche, Bäume und Karotten liefern mehr Ertrag, wenn sie die richtige Pflanzenbegleitung haben. Die gewünschte Begleitung ist für jede Pflanze individuell und nicht vorhersagbar. Zum Glück kann die Begleitvorliebe der Pflanze unter der Drohne mit `get_companion()` gemessen werden. Es gibt ein Tupel zurück, in dem das erste Element der Pflanzentyp ist, den sie als Begleitung möchte, und das zweite Element die Position, an der sie ihre Begleitung haben möchte.

`plant, (x, y) = get_companion()`

Beispielsweise, wenn du einen Busch pflanzt und dann `get_companion()` aufrufst, könnte es `(Entities.Carrot, (3, 5))` zurückgeben. Das bedeutet, dass dieser Busch gerne Karotten an der Position `(3,5)` hätte. Wenn du dort Karotten pflanzt und dann den Busch erntest, wird er mehr Holz liefern. Das Wachstumsstadium der Karotten spielt dabei keine Rolle.

Die Begleitvorliebe einer Pflanze kann `Entities.Grass`, `Entities.Bush`, `Entities.Tree` oder `Entities.Carrot` sein. Jede Pflanze wählt das zufällig und immer eine andere Pflanzenart als sie selbst. Die Position kann jede Position innerhalb von 3 Schritten der Pflanze sein, außer die eigene Position.

Wenn sich keine Pflanze unter der Drohne befindet, die eine Begleitvorliebe hat, gibt `get_companion()` `None` zurück.

Der Ertragsmultiplikator beträgt `5` plus die Anzahl der Polykultur-Upgrades.
