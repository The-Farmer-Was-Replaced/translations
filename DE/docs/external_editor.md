# Externer Editor
Der integrierte Texteditor im Spiel ist in der Regel ausreichend, um dieses Spiel zu spielen. Natürlich kann er jedoch nicht mit fortschrittlicheren Texteditoren wie Visual Studio Code konkurrieren.

Das Spiel speichert alle Code-Dateien als `.py`-Dateien, sodass du sie mit Python-Editoren bearbeiten kannst.
Beachte, dass dies nur der Bequemlichkeit dient. Die In-Game-Sprache ist eigentlich kein Python, aber sie ist nah genug, damit Python IntelliSense vernünftig funktioniert.
Du findest die Dateien im [Speicherordner](persistent_data_path/Saves).

Jeder Speicher enthält auch eine `__builtins__.py`-Datei, die eingebaute Python-Definitionen enthält, die den In-Game-Builtins entsprechen, um IntelliSense zu ermöglichen.
Das Spiel ignoriert Pythons Import-Anweisungen, sodass du sie hinzufügen kannst, um deinem externen Editor das Erkennen von Funktionsdefinitionen aus anderen Dateien zu ermöglichen.

Um externe Änderungen im Spiel sichtbar zu machen, ohne den Speicher neu laden zu müssen, musst du die Option "File Watcher" aktivieren. Wenn du Dateien extern erstellst oder löschst, musst du den Speicher dennoch neu laden, um sie zu sehen.

## Verwendung von VS Code
Visual Studio Code ist der empfohlene Code-Editor für die Verwendung mit The Farmer Was Replaced.

Du kannst es [hier](https://code.visualstudio.com/download) installieren.

Nach dem Herunterladen installiere die Python-Erweiterung in VS Code.

Öffne anschließend den [Ordner](persistent_data_path/Saves), der deine `.py`-Dateien enthält, in VS Code. Stelle sicher, dass du den gesamten Ordner öffnest und nicht nur einzelne Dateien, sonst funktioniert die `__builtins__.py`-Datei nicht.

Die Python-Erweiterung importiert Funktionen aus anderen Dateien nicht automatisch, wie es das Spiel tut. Um "nicht definiert" Warnungen im Editor zu vermeiden, wenn du Funktionen aus anderen Dateien aufrufst, musst du die Zeile

`from filename import *`

am Anfang jeder Datei hinzufügen, die die Funktionen dieser Datei aufruft (ersetze `filename` durch den Dateinamen).
Das Spiel ignoriert diese Anweisungen.

Stelle im Spiel sicher, dass die Option "File Watcher" eingeschaltet ist. Jetzt werden alle Änderungen, die du in VS Code speicherst, automatisch im Spiel angezeigt.

Das war's! Jetzt kannst du deinen Code in einem professionellen Code-Editor schreiben!
