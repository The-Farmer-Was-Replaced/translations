# Polyculture
Gras, Büsche, Bäume und Karotten liefern zehnmal mehr Ertrag, wenn sie den richtigen Pflanzenbegleiter haben. Die Begleiterpräferenz ist für jede einzelne Pflanze unterschiedlich und kann nicht vorhergesagt werden. Glücklicherweise kann die Begleiterpräferenz der Pflanze unter der Drohne mit `get_companion()` gemessen werden. Es gibt eine Liste zurück, bei der das erste Element der Typ der Pflanze ist, die sie als Begleiter haben möchte, und das zweite und dritte Element die x- und y-Koordinaten der Position sind, an der sie ihren Begleiter haben möchte.

Wenn Sie zum Beispiel einen Busch pflanzen und dann `get_companion()` aufrufen, wird etwas wie `[Entities.Carrots, 3, 5]` zurückgegeben. Das bedeutet, dass dieser Busch gerne Karotten an der Position `(3,5)` hätte. Wenn Sie also Karotten an `(3,5)` pflanzen und dann den Busch ernten, wird er zehnmal mehr Holz liefern. Das Wachstumsstadium der Karotte spielt keine Rolle.

Die Begleiterpräferenz einer Pflanze kann entweder `Entities.Grass`, `Entities.Bush`, `Entities.Tree` oder `Entities.Carrots` sein. Jede Pflanze wählt dies zufällig, aber sie wird immer eine andere Pflanze als sich selbst wählen. Die Position kann auch jede Position innerhalb von 3 Zügen der Pflanze sein, außer der Position der Pflanze selbst.

Wenn sich keine Pflanze unter der Drohne befindet, die eine Begleiterpräferenz hat, wird `get_companion()` `None` zurückgeben.
