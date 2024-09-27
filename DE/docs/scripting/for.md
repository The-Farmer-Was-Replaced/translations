# For Loop
Die `for`-Schleife funktioniert wie in Python. (In einigen Sprachen als foreach-Schleife bezeichnet, nicht zu verwechseln mit der C-ähnlichen for-Schleife, die etwas anderes ist).

`for i in sequence:
	#do something with i`

Ähnlich wie die `while`-Schleife ruft die `for`-Schleife auch wiederholt einen Codeblock auf. Anstatt basierend auf einer Bedingung zu schleifen, führt sie den Schleifenkörper einmal für jedes Element in einer Sequenz aus.

## Syntax
Eine for-Schleife sieht so aus:

`for variable_name in sequence:
	#code block`

`variable_name` kann jeder beliebige Name sein. Es ist eine Variable, die das aktuelle Element in der Sequenz speichert. `sequence` muss ein Wert sein, der iteriert werden kann, wie ein Bereich oder Zahlen. Der Codeblock wird für jedes Element mit der Schleifenvariablen ausgeführt, die diesem Element zugewiesen ist.

## Sequenzen
[Bereiche](functions/range)      <unlock=lists>[Listen](docs/scripting/lists.md)      </unlock><unlock=functions>[Tupel](docs/scripting/tuples.md)      </unlock><unlock=dicts>[Wörterbücher](docs/scripting/dicts.md)      </unlock><unlock=sets>[Mengen](docs/scripting/sets.md)</unlock>

## Beispiel
`for i in range(5):
	harvest()`

Diese Schleife führt den Körper eine feste Anzahl von Malen aus. Es ist im Wesentlichen dasselbe wie zu schreiben

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

Also ruft sie `harvest()` 5 Mal auf.

Siehe auch [Break](docs/scripting/break) und [Continue](docs/scripting/continue)
