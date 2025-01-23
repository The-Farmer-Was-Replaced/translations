# Chargement des Backups

Malheureusement, il arrive parfois qu'un fichier de sauvegarde soit corrompu ou que vous perdiez certains fichiers de code. Si cela vous arrive, vous pouvez essayer de charger un backup. Si cela se produit régulièrement, essayez de désactiver Steam Cloud.

Un backup est créé chaque fois que le jeu est sauvegardé, et un petit nombre de backups sont conservés au cas où vous auriez besoin de restaurer quelque chose.
Ces backups se trouvent dans le [répertoire de backup](persistent_data_path/Backup). Ce sont des copies des sauvegardes dans le [répertoire de sauvegarde](persistent_data_path/Saves).
Le moyen le plus simple de charger un backup est de copier le dossier du backup spécifique que vous souhaitez charger dans le répertoire de sauvegarde.

Une sauvegarde est un dossier avec un fichier `save.json` et une série de fichiers `.py`.
Si vous avez seulement perdu quelques fichiers de code, ou si les fichiers de code sont encore présents mais que le fichier `save.json` est corrompu, vous pouvez également remplacer seulement les parties corrompues par les fichiers correspondants du backup.
