# Irrgärten
`Items.Weird_Substance`, das durch [fertilizing](docs/unlocks/fertilizer.md) Pflanzen erhalten wird, hat eine seltsame Wirkung auf Büsche. Wenn sich die Drohne über einem Busch befindet und du `use_item(Items.Weird_Substance, amount)` aufrufst, verwandelt sich der Busch in ein Heckenlabyrinth.
Die Größe des Irrgartens hängt von der Menge an `Items.Weird_Substance` ab (das zweite Argument des Aufrufs von `use_item()`).
Ohne Irrgarten-Upgrades führt das Verwenden von `n` `Items.Weird_Substance` zu einem `n`x`n`-Labyrinth. Für jede Irrgarten-Upgrade-Stufe benötigst du zusätzlich `n` `Items.Weird_Substance`, um die gleiche Wirkung zu erzielen.
Um ein vollflächiges Labyrinth zu bauen:

`plant(Entities.Bush)
n_substance = get_world_size() * num_unlocked(Unlocks.Mazes)
use_item(Items.Weird_Substance, n_substance)`

Aus irgendeinem Grund kann die Drohne nicht über die Hecken fliegen, obwohl sie nicht sehr hoch aussehen.

Irgendwo im Labyrinth befindet sich ein Schatz. Verwende `harvest()` auf den Schatz, um Gold in Höhe der Labyrinthfläche zu erhalten. (Zum Beispiel bringt ein 5x5-Labyrinth 25 Gold.)

Bei Verwendung von `harvest()` an anderer Stelle verschwindet das Labyrinth einfach.

`get_entity_type()` ist gleich `Entities.Treasure`, wenn die Drohne sich über dem Schatz befindet, und `Entities.Hedge` überall sonst im Labyrinth.

Irrgärten enthalten keine Schleifen, es sei denn du verwendest den Irrgarten erneut (siehe unten, wie man ein Labyrinth wiederverwendet). Es gibt also keinen Weg, an denselben Ort zurückzugelangen, ohne umzukehren.

Du kannst überprüfen, ob eine Wand vorhanden ist, indem du versuchst, sie zu durchqueren.
`move()` gibt `True` zurück, wenn es erfolgreich war, und `False` andernfalls.

Wenn du keine Ahnung hast, wie du den Schatz erreichen sollst, wirf einen Blick auf Hinweis 1. Er zeigt dir, wie man ein solches Problem angehen kann.

Für eine zusätzliche Herausforderung kannst du den Irrgarten wiederverwenden, indem du erneut die gleiche Menge `Items.Weird_Substance` auf den Schatz anwendest.
Dadurch erhöht sich die Goldmenge im Schatz um ein vollständiges Labyrinth und er wird an eine zufällige Stelle im Labyrinth versetzt.

Wenn du `measure()` auf einen Schatz verwendest, erhältst du als Tupel die Position, an die er versetzt wird.
`next_x, next_y = measure()`

Jedes Mal, wenn der Schatz versetzt wird, kann eine zufällige Wand aus dem Irrgarten entfernt werden. So können beim erneuten Verwenden Schleifen entstehen.

Beachte, dass Schleifen im Labyrinth das Ganze erheblich erschweren, da du dann ohne Umkehr wieder an denselben Ort gelangen kannst.
Das Wiederverwenden eines Irrgartens bringt nicht mehr Gold ein, als wenn du ihn einfach aberntest und einen neuen spawnst.
Es ist zu 100% eine zusätzliche Herausforderung, die du problemlos überspringen kannst.
Es lohnt sich nur, wenn die zusätzlichen Informationen und Abkürzungen dir helfen, das Labyrinth schneller zu lösen.

Dasselbe Labyrinth kann maximal 300 Mal gelöst werden. Das entspricht 299 Versetzungen. Danach hat das Anwenden von weird substance auf den Schatz keine weitere Wirkung.

<spoiler=show hint 1>Hier ist ein allgemeines Vorgehen zur Lösung des Problems:

Erstelle ein Irrgarten und stelle dir vor, du wärst die Drohne.

Überlege, wie du versuchen würdest, den Schatz zu finden, wenn du dich im Irrgarten befindest.

Schreibe deine Strategie Schritt für Schritt auf, damit jemand anderes ihr folgen könnte, ohne nachzudenken.

Versuche nun, diese Schritte in Code umzusetzen.
</spoiler>
<spoiler=show hint 2>Solange es keine Schleifen gibt: Alle Mauern bilden eigentlich nur eine einzige zusammenhängende Wand. Wenn du der Wand folgst, führt sie dich durch das gesamte Labyrinth.
Diese Methode benötigt sehr wenig Code und du musst nicht verfolgen, wo du schon warst. Ungefähr 10 Codezeilen reichen aus.</spoiler>
<spoiler=show hint 3>Anstatt absolute Richtungen zu verwenden wie move `East` oder move `West`, kann es sehr nützlich sein, relative Richtungen zu verwenden, z.B. "nach rechts abbiegen" oder "nach links abbiegen". Dazu musst du speichern, in welche Richtung sich die Drohne gerade bewegt. Die Drohne dreht sich zwar nie wirklich, aber du kannst dennoch eine "virtuelle" Drehung im Code beibehalten.
Folgender Index-Trick ist hilfreich:

`directions = [North, East, South, West]
index = 0`

Verwende `% 4`, um eine "Uhrzeigerrotation" zu simulieren, damit es nach `West` wieder bei `North` weitergeht:
`# turn right
index = (index + 1) % 4`

`# turn left
index = (index - 1) % 4

move(directions[index])`
</spoiler>
<spoiler=show hint 4>Wenn du es nicht lösen kannst, kannst du es dir immer leicht machen und die weniger effiziente Methode anwenden.
Ein `1`x`1`-Labyrinth zu lösen ist trivial.
</spoiler>
