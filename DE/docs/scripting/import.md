
# Importieren
Das Platzieren Ihres gesamten Codes in einer einzigen Datei wird schnell unübersichtlich.
`import`-Anweisungen ermöglichen es Ihnen, Funktionen und globale Variablen aus einer anderen Datei zu importieren.

`import dateiname`

Dies ist die einfachste Form der Importanweisung. Sie gibt Ihnen Zugriff auf alles, was in der Datei mit dem Namen `dateiname` definiert ist. Jedes Fenster im Spiel ist eine Datei, und der Dateiname ist der im oberen Bereich des Fensters angezeigte Name.

Hier ist ein Beispiel mit zwei Dateien:
Datei namens helper:
`x = 0

def say_hello():
    print("hallo von helper")`

Andere Datei:
`import helper
helper.say_hello()
helper.x += 1`

Hier führt `import helper` die Datei mit dem Namen `helper` aus und gibt Ihnen Zugriff auf alle deren Globalen.
Sie können dann auf Variablen und Funktionen innerhalb des importierten Moduls mittels des `.` Operators zugreifen.
In diesem Beispiel ruft `helper.say_hello()` die Funktion `say_hello()` innerhalb von helper auf und die letzte Zeile inkrementiert die globale Variable x.

Sie können auch die Globals aus dem importierten Modul in den aktuellen Scope verschieben, in dem die Importanweisung ausgeführt wird, indem Sie die `from`-Syntax verwenden.

`from helper import *`
Importiert alle Globals aus helper.

oder

`from helper import say_hello`
Importiert nur die angegebenen Globals aus helper.

Dies importiert auch die helper-Datei, aber anstatt über eine Variable namens `helper` darauf zuzugreifen, entpackt es Globals aus `helper` und weist sie direkt im lokalen Scope zu.

`from helper import say_hello
say_hello()`

Diese Form des Imports wird normalerweise nicht empfohlen, da sie nicht gut funktioniert, wenn zwei Dateien einander importieren, und Sie möglicherweise versehentlich Variablen in der importierenden Datei aufgrund von Namenskonflikten überschreiben.

# Wie es wirklich funktioniert

## Kurzfassung
Imports können ziemlich unintuitiv sein, aber die meisten Probleme können vermieden werden, indem man sich an die `import datei`-Syntax hält, anstatt `from datei import` zu verwenden, und alles, was keine globale Definition ist, in
`if __name__ == "__main__":` einbettet.

## Import Seiteneffekte
Das erste Mal, dass Sie eine Datei importieren, wird die gesamte Datei ausgeführt und Sie haben dann Zugriff auf alle Variablen, die während der Ausführung definiert wurden.
Wenn Sie dieselbe Datei erneut importieren, wird einfach das zwischengespeicherte Modul vom ersten Mal zurückgegeben.

Das bedeutet, dass Importanweisungen Seiteneffekte haben können. Wenn Sie eine Datei importieren, die `harvest()` aufruft, wird tatsächlich beim Import geerntet. Aber wenn Sie sie erneut importieren, wird nicht erneut geerntet, da die Datei nur einmal ausgeführt wird.

Es gibt eine Möglichkeit, solche Seiteneffekte zu vermeiden, indem die Variable `__name__` verwendet wird. Diese Variable wird automatisch auf `"__main__"` gesetzt, wenn eine Datei direkt ausgeführt wird, und auf den Namen der Datei, wenn eine Datei über `import` ausgeführt wird.
Es ist gute Praxis, jeden Code, den Sie nicht ausführen möchten, wenn die Datei importiert wird, innerhalb eines `if __name__ == "__main__":` Blocks zu platzieren.

Eine übliche Dateistruktur in Python ist es, den Code, der ausgeführt werden soll, wenn die Datei ausgeführt wird, in eine `main()` Funktion zu legen. So haben Sie eine klare Trennung zwischen lokalen Variablen (definiert innerhalb von `main()`) und globalen Variablen, die importiert werden können (definiert außerhalb von `main()`).

`a_global_variable = "global"

def main():
    a_local_variable = "local"
    // Dinge tun

if __name__ == "__main__":
    main()`

## Import Zyklen
Was passiert, wenn Datei `a` Datei `b` importiert und Datei `b` Datei `a` importiert?

Datei `a`:
`import b
x = 0`

Datei `b`:
`import a
def f():
    print(a.x)`

Dies funktioniert einwandfrei. Angenommen, keine der beiden Dateien ist noch geladen, und jemand führt `import a` aus.

- `a` läuft bis zur Zeile `import b`.
- `b` läuft bis zur Zeile `import a`.
- Das Modul `a` existiert bereits, enthält aber nicht `x`, weil es nur bis zur Zeile `import b` ausgeführt wurde.
- `b` speichert eine Referenz auf das halbgeladene Modul `a` in einer Variable namens `a`.
- `b` führt die `def` Anweisung aus und speichert die Funktion `f()`.
- `a` setzt die Ausführung fort und initialisiert `x`.

Wenn jemand jetzt `b.f()` aufruft, wird korrekt `0` gedruckt, weil das Modul `a`, auf das `b` eine Referenz hat, nun vollständig geladen ist.

Betrachten Sie nun denselben Code unter Verwendung der `from`-Syntax.

Datei `a`:
`from b import *
x = 0`

Datei `b`:
`from a import *
def f():
    print(x)`

- `a` läuft bis zur Zeile `from b import *`.
- `b` läuft bis zur Zeile `from a import *`.
- Das Modul `a` existiert bereits, wurde aber noch nicht vollständig ausgeführt.
- `b` entpackt alles, was derzeit in `a` ist, in seinen eigenen globalen Scope. Zu diesem Zeitpunkt enthält `a` nichts, weil es die Zeile `x = 0` noch nicht erreicht hat, also wird nichts importiert.
- `b` führt die `def` Anweisung aus und speichert die Funktion `f()`.

Wenn jemand nun `b.f()` aufruft, erhält er einen Fehler, dass `x` im aktuellen Scope nicht existiert. Dies liegt daran, dass `b` diesmal keine Referenz auf das noch ladende `a` hat und keine Definitionen sieht, die nach dem Import hinzugefügt wurden.
