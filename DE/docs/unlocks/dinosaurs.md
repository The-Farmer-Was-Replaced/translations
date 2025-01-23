# Dinosaurier
Dinosaurier sind uralte, majestätische Kreaturen, die für alte Knochen gezüchtet werden können.

Leider sind Dinosaurier vor langer Zeit ausgestorben, sodass wir sie jetzt nur noch verkleiden können.
Zu diesem Zweck hast du den neuen Dinosaurierhut erhalten.

Der Hut kann mit
`change_hat(Hats.Dinosaur_Hat)`

ausgerüstet werden.

Leider sieht er auf der Werbung nicht ganz so aus...

Wenn du den Dinosaurierhut ausrüstest und genügend Kürbisse hast, wird automatisch ein [Apfel](objects/apple) gekauft und unter der Drohne platziert.
Jedes Mal, wenn du dich von einem Apfel entfernst, wächst der Schwanz des Dinosaurierhuts um ein Feld und, falls du genügend Gegenstände hast, wird ein neuer Apfel an einem zufälligen Ort gekauft und platziert.
Der Apfel kann nicht spawnen, wenn dort bereits etwas gepflanzt ist.

Der Schwanz des Dinosauriers wird hinter der Drohne hergezogen und füllt die vorherigen Felder, über die die Drohne bewegt wurde. Wenn eine Drohne versucht, auf den Schwanz zu bewegen, schlägt `move()` fehl und gibt `False` zurück.
Das letzte Segment des Schwanzes bewegt sich während der Bewegung aus dem Weg, sodass du dich darauf bewegen kannst. Wenn die Schlange jedoch das ganze Feld ausfüllt, kannst du dich nicht mehr bewegen. Du kannst überprüfen, ob die Schlange vollständig gewachsen ist, indem du prüfst, ob du dich nicht mehr bewegen kannst.

Die Verwendung von `measure()` auf einem Apfel gibt die Position des nächsten Apfels als Tupel zurück.

`next_x, next_y = measure()`

Wenn der Hut wieder ausgerüstet wird, indem ein anderer Hut ausgerüstet wird, wird der Schwanz geerntet.
Du erhältst Knochen, die dem Quadrat der Schwanzlänge entsprechen. Für einen Schwanz der Länge `n` erhältst du `n**2` `Items.Bone`.
Zum Beispiel:
Länge 1 => 1 Knochen
Länge 2 => 4 Knochen
Länge 3 => 9 Knochen
Länge 4 => 16 Knochen
Länge 16 => 256 Knochen
Länge 100 => 10000 Knochen

Der Dinosaurierhut ist sehr schwer, sodass `move()` 800 Ticks statt 200 benötigt, wenn er ausgerüstet ist. Allerdings wird die Anzahl der Ticks, die für `move()` verwendet werden, jedes Mal um 3% (abgerundet) reduziert, wenn du einen Apfel aufnimmst, weil ein längerer Schwanz dir beim Bewegen helfen kann.

Die folgende Schleife druckt die Anzahl der Ticks, die von `move()` nach einer beliebigen Anzahl von Äpfeln verwendet werden:

`ticks = 800
for i in range(100):
    print("ticks after ", i, " apples: ", ticks)
    ticks -= ticks * 0.03 // 1`

<spoiler=zeige Hinweis 1>Wenn du dich immer auf demselben Pfad bewegst, der das ganze Feld abdeckt, kannst du jedes Mal leicht eine vollständig gefüllte Feldschlange erhalten, weil du jeden freien Platz abdeckst, bevor du zu deinem Schwanz zurückkehrst. Es ist nicht sehr effizient, aber es funktioniert.</spoiler>
