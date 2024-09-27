# Éditeur Externe

L'éditeur de texte intégré au jeu est généralement suffisant pour jouer à ce jeu, mais bien sûr, il ne peut pas rivaliser avec des éditeurs de texte plus sophistiqués comme Visual Studio Code.

Le jeu enregistre tous les fichiers de code en tant que fichiers .py, vous pouvez donc les éditer avec des éditeurs Python. 
Notez que cela est uniquement pour votre commodité. Le langage du jeu n'est pas réellement Python, mais il est suffisamment proche pour que l'IntelliSense de Python fonctionne correctement dessus. Vous pouvez trouver les fichiers dans le [dossier de sauvegarde](persistent_data_path/Saves).

Chaque sauvegarde contient également un fichier `__builtins__.py`, qui contient des définitions Python intégrées correspondant aux intégrés du jeu pour activer IntelliSense. 
Le jeu ignorera les instructions d'importation de Python, vous pouvez donc les ajouter pour aider votre éditeur externe à détecter les définitions de fonctions d'autres fichiers.

Pour voir les modifications externes dans le jeu sans avoir à recharger la sauvegarde, vous devez activer l'option "File Watcher". Si vous créez ou supprimez des fichiers de manière externe, vous devrez tout de même recharger la sauvegarde pour les voir.

## Utilisation de VS Code
Visual Studio Code est l'éditeur de code recommandé pour être utilisé avec The Farmer Was Replaced.

Vous pouvez l'installer [ici](https://code.visualstudio.com/download).

Après l'avoir téléchargé, installez l'extension Python dans VS Code.

Une fois cela fait, ouvrez le [dossier](persistent_data_path/Saves) qui contient vos fichiers `.py` dans VS Code. Assurez-vous d'ouvrir le dossier entier, pas seulement les fichiers individuels, sinon le fichier `__builtins__.py` ne fonctionnera pas.

L'extension Python n'importe pas automatiquement les fonctions d'autres fichiers comme le fait le jeu. Donc, pour éviter d'obtenir des avertissements "non défini" dans l'éditeur lors de l'appel de fonctions d'autres fichiers, vous devrez ajouter la ligne

`from filename import *`

au début de chaque fichier qui appelle les fonctions de ce fichier (remplacez `filename` par le nom du fichier).
Le jeu ignorera ces instructions.

Dans le jeu, assurez-vous d'avoir activé l'option "File Watcher". Maintenant, chaque fois que vous sauvegardez dans VS Code, les modifications apparaîtront automatiquement dans le jeu.

C'est tout ! Maintenant, vous pouvez écrire votre code dans un éditeur de code professionnel !