
# Import
Wenn du deinen gesamten Code in eine einzige Datei packst, wird das schnell unüberschaubar.
`import`-Anweisungen erlauben dir, Funktionen und globale Variablen aus einer anderen Datei zu importieren.

`import filename`

Dies ist die einfachste Form eines Import-Statements. Es verschafft dir Zugriff auf alles, was in der Datei namens `filename` definiert wurde. Jedes Fenster im Spiel ist eine Datei, und der Dateiname ist der oben im Fenster angezeigte Name.

Ein Beispiel mit zwei Dateien:
Datei namens helper:
`def say_hello():
    print("hello from helper")`

Irgendeine andere Datei:
`import helper
helper.say_hello()`

Hier führt `import helper` die Datei helper aus und gibt dir Zugriff auf alle ihre globalen Variablen.
Dann kannst du Variablen und Funktionen innerhalb des importierten Moduls mit dem `.`-Operator aufrufen.
In diesem Beispiel ruft `helper.say_hello()` die Funktion `say_hello()` in helper auf.

Du kannst die globalen Variablen aus dem importierten Modul auch in den aktuellen Scope übertragen, in dem das Import-Statement ausgeführt wird, indem du die `from`-Syntax verwendest.

`from helper import *`
Importiert alle globalen Variablen aus helper.

oder

`from helper import say_hello`
Importiert nur die angegebenen globalen Variablen aus helper.

Dies lädt ebenfalls die helper-Datei, aber anstatt über eine Variable namens `helper` darauf zuzugreifen, werden die globalen Variablen aus `helper` direkt in den lokalen Scope übertragen.

`from helper import say_hello
say_hello()`

Diese Form des Imports wird normalerweise nicht empfohlen, da man ungewollt Variablen im Import-File überschreiben kann, falls Namenskonflikte entstehen.

## Was es tatsächlich macht
Wenn du eine Datei zum ersten Mal importierst, wird der gesamte Inhalt der Datei ausgeführt, und du erhältst Zugriff auf alle Variablen, die während der Ausführung definiert wurden.
Importierst du dieselbe Datei erneut, wird nur der zuvor zwischengespeicherte globale Zustand zurückgegeben.

Das bedeutet, dass Import-Statements Nebeneffekte haben können. Wenn du eine Datei importierst, die `harvest()` aufruft, wird tatsächlich während des Imports geerntet. Importierst du die Datei erneut, wird sie nicht erneut ausgeführt, da sie nur einmal ausgeführt wird.

Es gibt eine Möglichkeit, solche Nebeneffekte mit der Variable `__name__` zu vermeiden. Sie wird automatisch auf `"__main__"` gesetzt, wenn eine Datei direkt ausgeführt wird, und auf den Dateinamen, wenn sie über `import` läuft.
Es gilt als gute Praxis, allen Code, den du nicht beim Import ausführen möchtest, in einen `if __name__ == "__main__":`-Block zu setzen.

Eine übliche Dateistruktur in Python ist, den Code, der beim direkten Ausführen der Datei ausgeführt werden soll, in eine `main()`-Funktion zu packen. So hast du eine klare Trennung zwischen lokalen Skript-Variablen (innerhalb von `main()`) und globalen Variablen, die importiert werden können (außerhalb von `main()` definiert).

`a_global = "global value"

def main():
    a_local = "local value"
    //do things

if __name__ == "__main__":
    main()`
