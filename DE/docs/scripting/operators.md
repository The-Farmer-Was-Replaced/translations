# Operatoren
arithmetische Operatoren: `+, -, *, /, //, %, **`
vergleichende Operatoren: `==, !=, <=, >=, <, >`
boolesche Operatoren: `not, and, or`

Hinweis: Alle Zahlen im Spiel sind Gleitkommazahlen. Daher sind alle arithmetischen Operatoren Gleitkommaoperatoren.
`//` ist definiert, um die Zahl nach der Division einfach abzurunden.

Für Zuordnungsoperatoren musst du das "Variablen"-Unlock freischalten.

## Einführung
Operatoren ermöglichen es dir, Werte zu vergleichen, zu modifizieren und zu kombinieren.
Die arithmetischen Operatoren `+, -, *, /, //, %, **` werden verwendet, um gängige mathematische Operationen an Zahlen durchzuführen.
Die vergleichenden Operatoren `==, !=, <=, >=, <, >` werden verwendet, um Werte zu vergleichen. Das Ergebnis ist immer entweder `True` oder `False`.
Die logischen Operatoren (auch boolesche Operatoren genannt) `not, and, or` werden verwendet, um Wahrheitswerte zu kombinieren.

## Arithmetische Operatoren
`+` und `-` werden für Addition und Subtraktion verwendet.

`2 + 3` ergibt `5`
`3 - 2` ergibt `1`

`*`, `/` und `//` werden für Multiplikation und Division verwendet.

`2 * 3` ergibt `6`
`5 / 2` ergibt `2.5`

`//` macht dasselbe wie `/`, aber das Ergebnis wird abgerundet (auf die nächste ganze Zahl nach unten).

`5 // 2` ergibt `2`

`%` ist der Modulo-Operator, auch bekannt als Restoperator. Er teilt im Wesentlichen die beiden Zahlen und gibt dann den Rest zurück. Man kann es sich auch vorstellen, dass die rechte Zahl wiederholt von der linken Zahl subtrahiert wird, bis der Rest kleiner als die rechte Zahl ist.

`4 % 2` ergibt `0`
`5 % 2` ergibt `1`
`6 % 2` ergibt `0`
`2 % 6` ergibt `2`
`1.5 % 1` ergibt `0.5`

`**` ist der Potenzoperator.

`2**2` ergibt `4`
`(-5)**3` ergibt `-125`

## Vergleichende Operatoren
`==` und `!=` werden verwendet, um zu prüfen, ob zwei Werte "gleich" (`==`) oder "nicht gleich" (`!=`) sind. Sie können für alle Arten von Werten verwendet werden.

`2 == 2` ergibt `True`
`Entities.Bush != Entities.Bush` ergibt `False`
`3 != 3 + 1` ergibt `True`

`<=, >=, <, >` können nur für Zahlen verwendet werden. Sie prüfen, ob die linke Zahl "kleiner oder gleich" (`<=`), "größer oder gleich" (`>=`), "kleiner" (`<`) oder "größer" (`>`) als die rechte Zahl ist.

`1 <= 1` ergibt `True`
`2 >= 3` ergibt `False`
`-2 < -1` ergibt `True`
`6 > 6` ergibt `False`

## Boolesche Operatoren
`not` kehrt einfach den Wert um:

`not False` ergibt `True`
`not True` ergibt `False`

`and` ergibt `True` nur wenn beide Werte `True` sind

`True and True` ergibt `True`
`True and False` ergibt `False`
`False and False` ergibt `False`

`or` ergibt `True`, wenn mindestens einer der Werte `True` ist

`True or True` ergibt `True`
`True or False` ergibt `True`
`False or False` ergibt `False`
