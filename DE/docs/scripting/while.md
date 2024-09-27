# While Loop
Du hast die `while`-Schleife und die Werte `True` und `False` freigeschaltet. Die `while`-Schleife führt den Schleifenkörper so lange aus, wie die Bedingung `True` ist.

`while Bedingung:
	#Schleifenkörper`

Mach dir keine Sorgen über das Erstellen von Endlosschleifen. Die Verzögerungen in der Ausführung verhindern, dass das Programm einfriert.

## Für Anfänger
Vielleicht hast du bereits versucht, mehrere `harvest()`-Aufrufe hintereinander zu setzen:

`harvest()
harvest()
harvest()`

Dies ermöglicht es dir, mehrmals in einem Programmdurchlauf zu ernten.
Es wäre jedoch schön, mehr als dreimal zu ernten, und es ist schlechte Praxis, denselben Code mehrfach zu schreiben.
Die Lösung ist eine Schleife.
Eine Schleife ermöglicht es dir, denselben Code mehrfach auszuführen.

Die while-Schleife nimmt eine Bedingung, die ein logischer Wert ist, der nur in einem von zwei Zuständen sein kann: `True` oder `False`.
Ein solcher Wert wird als boolescher Wert bezeichnet.

Die Schleife führt dann den Code innerhalb der Schleife aus, bis die Bedingung `False` ist.
Die while-Schleife sieht so aus:

`while Bedingung:
	#Schleifenkörper
	#Schleifenkörper
	#...`

Dabei musst du "Bedingung" durch einen booleschen Wert ersetzen und `#Schleifenkörper` durch das, was du in der Schleife tun möchtest.

Es gibt zwei konstante boolesche Werte. Konstanten sind Werte, die sich während des Programms nicht ändern.

Um einen konstanten booleschen Wert zu erstellen, der immer `True` ist, kannst du einfach `True` schreiben. Schreibe `False` als konstanten booleschen Wert, der immer `False` sein wird.
Du könntest also entweder schreiben

`while False:
	do_a_flip()`

oder

`while True:
	do_a_flip()`

Das erste wird niemals einen Flip machen und das zweite wird für immer Flips machen (eine Endlosschleife).

Normalerweise ist es eine schlechte Idee, eine Endlosschleife zu erstellen, da sie das Programm einfrieren lässt, aber in diesem Spiel gibt es Verzögerungen zwischen jeder Iteration der Schleife, sodass die Drohne weiterhin Flips macht, bis du sie manuell stoppst, indem du erneut die Ausführen-Taste drückst.

Beachte, wie die Zeile nach dem Doppelpunkt eingerückt ist. Eine solche Einrückung wird verwendet, um Codeblöcke zu trennen.
Drücke einfach Tab, um eine Einrückung hinzuzufügen, und Shift + Tab (oder Backspace), um sie zu entfernen.

Die Schleife wird alle eingerückten Anweisungen nach dem Doppelpunkt wiederholen.
Anweisungen nach dem eingerückten Block werden ausgeführt, nachdem die Schleife beendet ist.
