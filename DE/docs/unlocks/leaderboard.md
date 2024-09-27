# Leaderboard
Die ultimative Herausforderung der automatisierten Landwirtschaft besteht darin, das Spiel so schnell wie möglich automatisch durchzuspielen.

Der Aufruf von `timed_reset()` speichert das Spiel, setzt alle Freischaltungen und Upgrades zurück, die nicht mit Programmierung zu tun haben, und startet den Leaderboard-Timer.

Sie behalten alle Sprachfunktionen wie `while, if, for`, Variablen, Operatoren und Sensoren.
Sie behalten auch die Kosten und automatischen Freischaltungen, sodass Sie das Spielen des Spiels vollständig automatisieren können.

Wenn die Programmausführung stoppt, wird der Lauf abgebrochen.
Der Lauf ist beendet, wenn die Ausführung erneut `timed_reset()` aufruft.
Sie müssen nicht alles freigeschaltet haben, versuchen Sie einfach, `Unlocks.Leaderboard` freizuschalten und `timed_reset()` so schnell wie möglich aufzurufen.

Nach dem Ende oder Abbruch des Laufs wird der Spielstand von vor dem Lauf wieder geladen.

Während der Timer läuft, haben Sie die Möglichkeit, die Zeit zu beschleunigen, damit Sie nicht so lange warten müssen.

Denken Sie daran, dass Sie `num_unlocked(unlock) > 0` verwenden können, um zu überprüfen, ob etwas freigeschaltet ist, und Sie können `get_cost()` für Ihre Freischaltungen verwenden, um zu sehen, was sie kosten, damit Sie automatisch die richtigen Gegenstände farmen können.
