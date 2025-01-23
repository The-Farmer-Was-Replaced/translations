# Debug

Manchmal funktioniert dein Code einfach nicht und du musst herausfinden, warum. Es gibt ein paar Werkzeuge, die dir dabei helfen.

Das Erste ist, das Programm Schritt für Schritt auszuführen.
Du kannst den Schritt-für-Schritt-Modus mit dem Button neben dem Ausführen-Button aktivieren oder einen Haltepunkt setzen.

Haltepunkte können hinzugefügt werden, indem du auf das Haltepunktfeld links des Codes klickst.
![](Breakpoints227)
Wenn die Ausführung die Zeile mit dem Haltepunkt erreicht, wechselt es automatisch in den Schritt-für-Schritt-Modus.

Wenn du über eine Variable fährst, wird ihr aktueller Wert angezeigt.

Die `print()` Funktion kann auch sehr nützlich sein. Sie druckt jeden übergebenen Wert direkt in die Luft.

Beispiele:

`print(0.24) #druckt "0.24"

print(can_harvest()) #druckt "True" oder "False"

print(get_pos_x(), get_pos_y()) #druckt die aktuelle Position`

Die print-Funktion druckt den Wert direkt in die Luft und auf die [Ausgabe](docs/output.md) Seite.

In die Luft zu drucken kann manchmal etwas langsam sein, wenn du viele Werte drucken möchtest.
In diesem Fall kannst du die `quick_print()` Funktion verwenden, die nur im Ausgabefenster druckt.

Das Ausgabefenster protokolliert auch Warnungen und Fehler, daher kann es nützlich sein, dies zu überprüfen, wenn etwas nicht wie erwartet funktioniert.

Wenn die Ausführung stoppt, wird die Ausgabe auch in die output.txt Datei im Spielordner geschrieben. Du findest den Spielordner, indem du Menü -> Laden -> Ordner öffnen auswählst.
