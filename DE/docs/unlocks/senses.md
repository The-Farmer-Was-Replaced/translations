# Sinne
Die Drohne kann jetzt sehen!

Die Funktionen `get_pos_x()` und `get_pos_y()` geben die aktuelle x- und y-Position der Drohne zurück. An der Startposition sind beide `0`. Die x-Position erhöht sich um `1` pro Feld Richtung `East` und die y-Position erhöht sich um `1` pro Feld Richtung `North`.

`num_items(item)` gibt zurück, wie viele von einem Item du hast.
Zum Beispiel gibt `num_items(Items.Hay)` zurück, wie viel Heu du hast.

`get_entity_type()` und `get_ground_type()` geben den Typ der Entität oder des Bodens zurück, der sich unter der Drohne befindet.

Mache einen Flip, wenn du über einem Busch bist:
`if get_entity_type() == Entities.Bush:
    do_a_flip()`

Das `None` Schlüsselwort ist jetzt auch freigeschaltet! `None` ist ein Wert, der repräsentiert, dass kein Wert vorhanden ist.
Zum Beispiel gibt eine Funktion, die keine `return`-Anweisung hat, tatsächlich `None` zurück.

`get_entity_type()` gibt `None` zurück, wenn sich keine Entität unter der Drohne befindet.
