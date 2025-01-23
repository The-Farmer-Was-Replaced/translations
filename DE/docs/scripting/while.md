# While-Schleife
Du hast die `while`-Schleife sowie die Werte `True` und `False` freigeschaltet. Die `while`-Schleife führt den Schleifenrumpf so lange aus, wie die Bedingung `True` ist.

`while condition:
	#loop body`

Mach dir keine Sorgen über endlose Schleifen. Die Verzögerungen bei der Ausführung verhindern, dass das Programm einfriert.

## Für Anfänger
Vielleicht hast du bereits versucht, mehrere `harvest()`-Aufrufe hintereinander zu setzen:

`harvest()
harvest()
harvest()`

Dies ermöglicht es dir, mehrere Male in einem Programmlauf zu ernten.
Es wäre jedoch schön, mehr als dreimal zu ernten, und denselben Code mehrfach zu schreiben ist schlechte Praxis.
Die Lösung ist eine Schleife.
Eine Schleife erlaubt es dir, denselben Code mehrfach auszuführen.

Die while-Schleife nimmt eine Bedingung, die ein logischer Wert ist und nur in einem von zwei Zuständen sein kann: `True` oder `False`.
Ein solcher Wert wird als Boolescher Wert bezeichnet.

Die Schleife führt dann den Code innerhalb der Schleife aus, bis die Bedingung False ist.
Die while-Schleife sieht so aus:

`while condition:
	#loop body
	#loop body
	#...`

Dabei musst du "condition" durch einen Booleschen Wert ersetzen und `#loop body` durch das, was du in der Schleife machen möchtest.

Es gibt zwei konstante boolesche Werte verfügbar. Konstanten sind Werte, die sich während des Programms nie ändern.

Um einen konstanten booleschen Wert zu erstellen, der immer `True` ist, kannst du einfach `True` schreiben. Schreibe `False` als konstanten booleschen Wert, der immer `False` ist.
Du könntest also entweder schreiben

`while False:
	do_a_flip()`

oder

`while True:
	do_a_flip()`

Die erste führt niemals einen Flip aus und die zweite führt Flips für immer aus (eine endlose Schleife).

Normalerweise ist das Erstellen einer endlosen Schleife eine schlechte Idee, weil es das Programm einfrieren lässt, aber in diesem Spiel gibt es Verzögerungen zwischen jeder Iteration der Schleife, sodass die Drohne weiterhin einen Flip ausführt, bis du sie manuell stoppst, indem du die Ausführungsschaltfläche erneut drückst.

Beachte, wie die Zeile nach dem Doppelpunkt eingerückt ist. Solche Einrückungen werden verwendet, um Codeblöcke zu trennen.
Drücke einfach Tab, um die Einrückung hinzuzufügen, und Shift + Tab (oder Backspace), um sie zu entfernen.

Die Schleife wiederholt alle eingerückten Anweisungen nach dem Doppelpunkt.
Anweisungen nach dem eingerückten Block werden ausgeführt, nachdem die Schleife beendet wurde.
