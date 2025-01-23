# Sonnenblumen
[Sonnenblumen](objects/sunflower) sammeln die Kraft der Sonne. Diese Kraft kannst du ernten.

Das Pflanzen funktioniert genauso wie bei Karotten oder Kürbissen.

Das Ernten einer ausgewachsenen Sonnenblume liefert Energie.
Wenn mindestens 10 Sonnenblumen auf der Farm stehen und du die mit der größten Anzahl an Blütenblättern erntest, erhältst du 5-mal mehr Energie!

`measure()` gibt die Anzahl der Blütenblätter der Sonnenblume unter der Drohne zurück.
Sonnenblumen haben mindestens `7` und höchstens `15` Blütenblätter.
Sie können bereits vor dem vollständigen Wachstum gemessen werden.

Mehrere Sonnenblumen können die gleiche Anzahl an Blütenblättern haben, sodass es auch mehrere Sonnenblumen mit der größten Anzahl an Blütenblättern geben kann. In diesem Fall spielt es keine Rolle, welche davon du erntest.

Solange du Energie hast, läuft die Drohne doppelt so schnell.
Sie verbraucht alle 30 Aktionen (wie Bewegungen, Ernten, Pflanzen...) 1 Energie.
Die Ausführung anderer Codeanweisungen kann auch Energie verbrauchen, aber deutlich weniger als Drohnenaktionen.

Grundsätzlich wird alles, was durch Geschwindigkeits-Upgrades beschleunigt wird, auch durch Energie beschleunigt.
Alles, was durch Energie beschleunigt wird, verbraucht auch Energie proportional zur Ausführungszeit, unabhängig von Geschwindigkeits-Upgrades.
