# Name Scopes
Scopes bestimmen, welche Variablen von wo aus zugänglich sind. Ein Scope ist im Grunde eine Zuordnung von Namen zu Werten.
Sie funktionieren fast genauso wie in Python, aber nicht immer, also lesen Sie diesen Abschnitt sorgfältig durch.

Genau wie in Python gibt es einen globalen Scope, und jede Funktion hat einen lokalen Scope.
Wenn Sie eine Variable definieren, wird sie dem aktuellen Scope hinzugefügt.
Alles außerhalb einer Funktionsdefinition wird als Teil des globalen Scopes betrachtet.

`x = 1`
Weist dem Namen `x` im globalen Scope den Wert `1` zu.

Diese `def`-Anweisung weist dem Namen `f` im globalen Scope eine Funktion zu.
`def f():
    `Weist dem Namen `y` im lokalen Scope von `f` den Wert `1` zu.`
    y = 1

    `Weist dem Namen `g` im lokalen Scope von `f` eine Funktion zu.`
    def g():
        pass`

`f()`
Ruft die im globalen Scope gespeicherte Funktion `f` ab und ruft sie auf.

`print(y)`
Diese print-Anweisung im globalen Scope wirft einen Fehler, weil `y` nie im globalen Scope deklariert wurde, sodass wir es hier nicht lesen können.
Es existierte nur im lokalen Scope von `f`.

Schleifen und Verzweigungen erstellen keine eigenen Scopes, sodass alles, was innerhalb von ihnen deklariert wird, auch außerhalb verwendet werden kann.

`for i in range(3):
    pass
print(i)`

Dies wird `2` ausgeben, weil die letzte Iteration der `for`-Schleife `2` an `i` zugewiesen hat.

Bis hierher ist alles wie in Python. Der erste Unterschied besteht darin, wie globale Definitionen aus anderen Dateien importiert werden. Python verwendet dafür die import-Anweisung, das Spiel importiert globale Funktionen automatisch.

Alle in geladenen Dateien definierten Funktionen werden vor der Ausführung dem globalen Scope hinzugefügt, sodass Sie Funktionen verwenden können, die in anderen Dateien deklariert sind.
Beachten Sie, dass dies nicht für globale Variablen gilt. Sie sind nur verfügbar, wenn die Zeile, in der sie zugewiesen werden, tatsächlich ausgeführt wird. Nur der globale Scope des Fensters, auf das Sie die Ausführen-Schaltfläche klicken, wird ausgeführt.

Variablen aus dem globalen Scope können überall gelesen werden, aber Zuweisungen werden immer dem lokalen Scope zugewiesen.

`x = 1

def f():
    x += 1

f()

print(x)`

Dieser Code gibt `1` und nicht `2` aus, weil `x += 1` zuerst `1` aus der globalen Variable `x` liest und dann `2` einer neuen lokalen Variablen zuweist, die ebenfalls `x` genannt wird.
Die globale Variable `x` wird also nie geändert.

Dieses Verhalten unterscheidet sich leicht von dem von Python.
Python wirft hier einen Fehler, weil Sie versuchen, aus einer lokalen Variablen zu lesen, bevor sie zugewiesen wird.

In Python ist es auch möglich, das Schlüsselwort 'global' zu verwenden, um zu deklarieren, dass Sie die globale Variable anstelle der lokalen verwenden möchten, aber dies wird in diesem Spiel nicht unterstützt.

Wenn Sie wirklich globale Variablen aktualisieren müssen, können Sie dafür ein Wörterbuch verwenden.
Sie verwenden Referenzsemantik, was bedeutet, dass die Variable einen Verweis auf das zugrunde liegende Wörterbuch hält, anstatt die Datenstruktur direkt in der Variablen zu speichern.
Eine globale Variable kann einen Verweis auf ein Wörterbuch speichern, das in einer Funktion gelesen werden kann.
Sie können das zugrunde liegende Wörterbuch ändern, ohne die Variable im globalen Scope zu aktualisieren.
Da die Variable im globalen Scope immer noch auf dasselbe Wörterbuch zeigt, werden auch alle Änderungen an diesem Wörterbuch widergespiegelt. Um dies zu veranschaulichen, betrachten Sie den folgenden Code:

Weisen Sie ein Wörterbuch im globalen Scope zu
`d = {"x": 1}

def f():
    `Ändern Sie das Wörterbuch, auf das `d` verweist.`
    d["x"] += 1

`gibt `2` aus
print(d["x"])`
