# External Editor
Der im Spiel integrierte Texteditor ist normalerweise ausreichend, um dieses Spiel zu spielen, aber natürlich kann er nicht mit fortschrittlicheren Texteditoren wie Visual Studio Code konkurrieren.

Das Spiel speichert alle Code-Dateien als .py-Dateien, sodass Sie sie mit Python-Editoren bearbeiten können.
Beachten Sie, dass dies nur aus Bequemlichkeit geschieht. Die im Spiel verwendete Sprache ist nicht wirklich Python, aber sie ist nah genug dran, dass Python IntelliSense einigermaßen gut funktioniert.
Sie finden die Dateien im [Speicherordner](persistent_data_path/Saves).

Jeder Speicherstand enthält auch eine `__builtins__.py`-Datei, die eingebaute Python-Definitionen enthält, die den eingebauten Funktionen im Spiel entsprechen, um IntelliSense zu ermöglichen.
Das Spiel ignoriert Pythons Import-Anweisungen, sodass Sie diese hinzufügen können, um Ihrem externen Editor zu helfen, Funktionsdefinitionen aus anderen Dateien zu erkennen.

Um externe Änderungen im Spiel zu sehen, ohne den Speicherstand neu laden zu müssen, müssen Sie die Option "Dateiüberwachung" aktivieren. Wenn Sie Dateien extern erstellen oder löschen, müssen Sie den Speicherstand dennoch neu laden, um sie zu sehen.

## Verwendung von VS Code
Visual Studio Code ist der empfohlene Code-Editor für die Verwendung mit The Farmer Was Replaced.

Sie können es [hier](https://code.visualstudio.com/download) herunterladen.

Nach dem Herunterladen installieren Sie die Python-Erweiterung in VS Code.

Sobald Sie dies getan haben, öffnen Sie den [Ordner](persistent_data_path/Saves), der Ihre `.py`-Dateien in VS Code enthält. Stellen Sie sicher, dass Sie den gesamten Ordner öffnen und nicht nur die einzelnen Dateien, da sonst die `__builtins__.py`-Datei nicht funktioniert.

Die Python-Erweiterung importiert Funktionen aus anderen Dateien nicht automatisch wie das Spiel. Um also "nicht definiert"-Warnungen im Editor zu vermeiden, wenn Sie Funktionen aus anderen Dateien aufrufen, müssen Sie die Zeile

`from filename import *`

oben in jede Datei einfügen, die die Funktionen dieser Datei aufruft (ersetzen Sie `filename` durch den Namen der Datei).
Das Spiel ignoriert diese Anweisungen.

Stellen Sie im Spiel sicher, dass Sie die Option "Dateiüberwachung" aktiviert haben. Jetzt werden die Änderungen jedes Mal, wenn Sie in VS Code speichern, automatisch im Spiel angezeigt.

Das war's! Jetzt können Sie Ihren Code in einem professionellen Code-Editor schreiben!
