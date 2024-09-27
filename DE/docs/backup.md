# Loading Backups
Leider kommt es manchmal vor, dass eine Speicherdatei beschädigt wird oder einige Code-Dateien verloren gehen. Wenn dies bei Ihnen der Fall ist, können Sie versuchen, ein Backup zu laden. Wenn dies regelmäßig passiert, versuchen Sie, die Steam-Cloud auszuschalten.

Bei jedem Speichern des Spiels wird ein Backup erstellt, und es werden eine kleine Anzahl von Backups aufbewahrt, falls Sie etwas wiederherstellen müssen.
Diese Backups finden Sie im [Backup-Verzeichnis](persistent_data_path/Backup). Es handelt sich dabei um Kopien der Speicherstände im [Speicherverzeichnis](persistent_data_path/Saves).
Der einfachste Weg, ein Backup zu laden, besteht darin, den Ordner des spezifischen Backups, das Sie laden möchten, in das Speicherverzeichnis zu kopieren.

Ein Speicherstand ist ein Ordner mit einer `save.json`-Datei und einer Reihe von `.py`-Dateien.
Wenn Sie nur ein paar Code-Dateien verloren haben oder die Code-Dateien noch vorhanden sind, aber die `save.json`-Datei beschädigt ist, können Sie auch nur die beschädigten Teile durch die entsprechenden Dateien aus dem Backup ersetzen.
