# Sunflowers
Sonnenblumen sammeln die Kraft der Sonne. Du kannst diese Kraft ernten.

Das Pflanzen funktioniert genauso wie das Pflanzen von Karotten, außer dass du Sonnenblumensamen anstelle von Karottensamen kaufen musst.

Wenn du jedoch eine Sonnenblume erntest, fließt die Kraft aller Sonnenblumen auf dem Bauernhof in die geerntete Pflanze.
Das Ernten einer Sonnenblume ergibt somit eine Kraft, die der Quadratwurzel der Anzahl der Sonnenblumen auf dem Bauernhof entspricht.
Nur eine der Sonnenblumen mit den meisten Blütenblättern kann dies bewältigen.
Wenn du eine Sonnenblume erntest, die nicht die meisten Blütenblätter aller Sonnenblumen auf dem Bauernhof hat, wird die Kraft alle Sonnenblumen auf dem Bauernhof zerstören.

`measure()` gibt die Anzahl der Blütenblätter der Sonnenblume unter der Drohne zurück.
Sonnenblumen haben mindestens `7` und höchstens `15` Blütenblätter.
Sie können gemessen werden, bevor sie vollständig gewachsen sind.

Mehrere Sonnenblumen können die gleiche Anzahl von Blütenblättern haben, sodass es auch mehrere Sonnenblumen mit der größten Anzahl von Blütenblättern geben kann. In diesem Fall ist es egal, welche von ihnen du erntest.

Solange du Kraft hast, wird die Drohne sie nutzen, um doppelt so schnell zu arbeiten.
Sie verbraucht 1 Kraft alle 30 Aktionen (wie Bewegungen, Ernten, Pflanzen...).
Das Ausführen anderer Code-Anweisungen kann auch Kraft verbrauchen, aber viel weniger als Drohnenaktionen.

Im Allgemeinen wird alles, was durch Geschwindigkeits-Upgrades beschleunigt wird, auch durch Kraft beschleunigt.
Alles, was durch Kraft beschleunigt wird, verbraucht auch Kraft proportional zur Zeit, die es zur Ausführung benötigt, wobei Geschwindigkeits-Upgrades ignoriert werden.
