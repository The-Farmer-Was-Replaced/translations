# Namensbereiche
Scopes bestimmen, welche Variablen von wo aus zugänglich sind. Ein Scope ist im Grunde eine Zuordnung von Namen zu Werten.
Sie funktionieren im Grunde genauso wie in Python.

Es gibt einen globalen Scope und jeder Funktion einen lokalen Scope.
Wenn du eine Variable definierst, wird sie dem aktuellen Scope hinzugefügt.
Alles außerhalb einer Funktionsdefinition wird als Teil des globalen Scopes betrachtet.

`x = 1`
Weist dem Namen `x` im globalen Scope den Wert `1` zu.

Diese `def`-Anweisung weist eine Funktion dem Namen `f` im globalen Scope zu.
`def f():
    `Weist dem Namen `y` im lokalen Scope von `f` den Wert `1` zu.`
    y = 1

    `Weist dem Namen `g` im lokalen Scope von `f` eine Funktion zu.`
    def g():
        pass`

`f()`
Ruft die in `f` im globalen Scope gespeicherte Funktion auf.

`print(y)`
Diese print-Anweisung im globalen Scope wirft einen Fehler, weil `y` im globalen Scope nie deklariert wurde und daher hier nicht gelesen werden kann.
Es existierte nur im lokalen Scope von `f`.

## Das global-Schlüsselwort
Standardmäßig binden alle Variablen in Funktionen an den lokalen Scope, auch wenn eine Variable mit demselben Namen im globalen Scope existiert.

`x == 0

def f():
    x = 1
f()
print(x)`

Dieser Code gibt `0` aus, weil das lokale `x` innerhalb von `f` nicht dieselbe Variable ist wie das globale `x`, sodass das globale `x` unverändert bleibt. Dies ist wichtig, da ansonsten ein Funktionsaufruf versehentlich eine globale Variable überschreiben könnte, die zufällig denselben Namen wie eine lokale Variable dieser Funktion hat.

Wenn du eine globale Variable schreiben möchtest, musst du dies explizit mit dem `global`-Schlüsselwort tun.

`x == 0

def f():
    global x
    x = 1
f()
print(x)`

In diesem Beispiel bindet `global x` `x` an die oben definierte globale Variable `x`. Dies gibt jetzt `1` aus.
Beachte, dass das Ändern globaler Variablen normalerweise der erste Schritt hin zu spaghettiartigem Code ist, bei dem jeder Teil des Programms jeden anderen Teil beeinflusst. Verwende es also nicht übermäßig.

## Schleifen und Verzweigungen
Schleifen und Verzweigungen erzeugen keine eigenen Scopes, sodass alles, was innerhalb von ihnen deklariert wird, weiterhin außerhalb verwendet werden kann.

`for i in range(3):
    pass
print(i)`

Dies gibt `2` aus, weil die letzte Iteration der `for`-Schleife `2` an `i` zugewiesen hat.
