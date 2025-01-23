# For-Schleife
Die `for`-Schleife funktioniert wie in Python. (In einigen Sprachen als foreach-Schleife bezeichnet, nicht zu verwechseln mit der C-Style for-Schleife, die eine andere Sache ist).

`for i in sequence:
	#do something with i`

Ähnlich wie die `while`-Schleife ruft die `for`-Schleife ebenfalls wiederholt einen Block von Code auf. Anstatt basierend auf einer Bedingung zu schleifen, führt sie den Schleifenrumpf einmal für jedes Element in einer Sequenz aus.

## Syntax
Eine for-Schleife sieht so aus:

`for variable_name in sequence:
	#code block`

`variable_name` kann jeder von dir gewählte Name sein. Es ist eine Variable, die das aktuelle Element in der Sequenz speichert. `sequence` muss ein Wert sein, der iteriert werden kann, wie ein Bereich oder Zahlen. Der Codeblock wird für jedes Element ausgeführt, wobei die Schleifenvariable auf dieses Element gesetzt wird.

## Sequenzen
[Ranges](functions/range)      <unlock=lists>[Listen](docs/scripting/lists.md)      </unlock><unlock=functions>[Tuples](docs/scripting/tuples.md)      </unlock><unlock=dicts>[Dictionaries](docs/scripting/dicts.md)      </unlock><unlock=sets>[Sets](docs/scripting/sets.md)</unlock>

## Beispiel
`for i in range(5):
    harvest()`

Diese Schleife führt den Körper eine feste Anzahl von Malen aus. Es ist im Wesentlichen dasselbe wie das Schreiben von

`i = 0
harvest()
i = 1
harvest()
i = 2
harvest()
i = 3
harvest()
i = 4
harvest()`

Also ruft es `harvest()` 5 Mal auf.

Siehe auch [Break](docs/scripting/break.md) und [Continue](docs/scripting/continue.md)
