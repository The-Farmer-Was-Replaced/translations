# Carrots
Bevor du Karotten mit `plant(Entities.Carrots)` pflanzen kannst, musst du zwei neue Dinge tun. Erstens können Karotten nur auf gepflügtem Boden wachsen. Um den Boden zu pflügen, rufe einfach `till()` auf. Wenn du `till()` erneut aufrufst, wird der Boden wieder zu `Grounds.Turf`.

Die zweite neue Funktion ist, dass Karotten Samen zum Wachsen benötigen. Du kannst Karottensamen mit der neuen `trade()`-Funktion kaufen.
Du musst einen Gegenstandstyp an `trade()` übergeben, so: `trade(Items.Carrot_Seed)`

Wenn der Gegenstand gekauft werden kann, wird er damit gekauft.

Du kannst die Kosten eines Gegenstands in seinem Tooltip sehen. Der Tooltip erscheint, wenn du mit der Maus über den Gegenstand selbst oder den Gegenstandsnamen im Code fährst.
