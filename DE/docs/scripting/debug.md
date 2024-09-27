# Debug
Manchmal funktioniert Ihr Code einfach nicht und Sie müssen herausfinden, warum. Es gibt ein paar Werkzeuge, die Ihnen dabei helfen können.

Das erste ist, das Programm Schritt für Schritt auszuführen.
Sie können in den Schritt-für-Schritt-Modus wechseln, indem Sie auf die Schaltfläche neben der Ausführen-Schaltfläche klicken oder einen Haltepunkt setzen.

Haltepunkte können hinzugefügt werden, indem Sie auf das Haltepunkt-Panel links vom Code klicken.
![](Breakpoints227)
Wenn die Ausführung die Zeile erreicht, in der sich der Haltepunkt befindet, wechselt sie automatisch in den Schritt-für-Schritt-Modus.

Wenn Sie mit der Maus über eine Variable fahren, wird deren aktueller Wert angezeigt.

Die `print()`-Funktion kann ebenfalls sehr nützlich sein. Sie gibt jeden Wert, der an sie übergeben wird, direkt in die Luft aus.

Beispiele:

`print(0.24) #druckt "0.24"

print(can_harvest()) #druckt "True" oder "False"

print(get_pos_x(), get_pos_y()) #druckt die aktuelle Position`

Die print-Funktion gibt den Wert direkt in die Luft und auf die [Ausgabe](docs/output.md)-Seite aus.

Das Drucken in die Luft kann manchmal etwas langsam sein, wenn Sie viele Werte drucken möchten.
In diesem Fall können Sie die `quick_print()`-Funktion verwenden, die nur im Ausgabefenster druckt.

Das Ausgabefenster protokolliert auch Warnungen und Fehler, daher kann es nützlich sein, dies zu überprüfen, wenn etwas nicht wie erwartet funktioniert.

Wenn die Ausführung stoppt, wird die Ausgabe auch in die Datei output.txt im Spielordner geschrieben. Sie können den Spielordner finden, indem Sie Menü -> Laden -> Ordner öffnen auswählen.
