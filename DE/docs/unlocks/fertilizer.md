# Fertilizer
Irgendwann reicht es nicht mehr aus, nur abzuwarten, bis die Pflanzen wachsen.
Ähnlich wie Wasser erhältst du automatisch alle 10 Sekunden 1 Dünger, plus einen zusätzlichen für jedes Upgrade.

Dünger lässt Pflanzen augenblicklich wachsen. `use_item(Items.Fertilizer)` reduziert die verbleibende Wachstumszeit der Pflanze unter der Drohne um 2 Sekunden.

Dies hat einige Nebenwirkungen.
Pflanzen, die mit Dünger gezüchtet wurden, werden infiziert.

Wenn eine Pflanze infiziert ist, wird die Hälfte ihres Ertrags in `Items.Weird_Substance` umgewandelt, wenn sie geerntet wird.
Weird Substance kann auch auf Pflanzen angewendet werden, was den Effekt hat, den Infektionsstatus der Pflanze und aller benachbarten Pflanzen umzuschalten.

Wenn du also `use_item(Items.Weird_Substance)` auf eine infizierte Pflanze anwendest, wird sie geheilt, aber wenn du es auf eine gesunde Pflanze anwendest, wird sie infiziert.

Wenn du es auf eine infizierte Pflanze anwendest, die gesunde Nachbarn hat, wird die Pflanze geheilt, aber die Nachbarn werden infiziert und umgekehrt.
