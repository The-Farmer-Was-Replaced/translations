# Éditeur Externe
L'éditeur de texte intégré au jeu est généralement suffisant pour jouer, mais bien sûr il ne peut pas rivaliser avec des éditeurs de texte plus sophistiqués comme Visual Studio Code.

Le jeu enregistre tous les fichiers de code en tant que fichiers `.py`, vous pouvez donc les modifier avec des éditeurs Python.
Notez que ceci est uniquement pour des raisons de commodité. Le langage du jeu n'est en réalité pas Python, mais il est suffisamment proche pour que Python IntelliSense fonctionne correctement.
Vous pouvez trouver les fichiers dans le [dossier de sauvegarde](persistent_data_path/Saves).

Chaque sauvegarde contient également un fichier `__builtins__.py`, qui contient des définitions Python intégrées correspondant aux intégrées du jeu pour permettre IntelliSense.
Le jeu ignorera les instructions d'importation de Python, vous pouvez donc les ajouter pour aider votre éditeur externe à détecter les définitions de fonctions provenant d'autres fichiers.

Pour voir les changements externes dans le jeu sans avoir à recharger la sauvegarde, vous devez activer l'option "File Watcher". Si vous créez ou supprimez des fichiers en externe, vous devrez toujours recharger la sauvegarde pour les voir.

## Utiliser VS Code
Visual Studio Code est l'éditeur de code recommandé pour utiliser avec The Farmer Was Replaced.

Vous pouvez l'installer [ici](https://code.visualstudio.com/download).

Après l'avoir téléchargé, installez l'extension Python dans VS Code.

Une fois cela fait, ouvrez le [dossier](persistent_data_path/Saves) contenant vos fichiers `.py` dans VS Code. Assurez-vous d'ouvrir tout le dossier, pas seulement les fichiers individuels, sinon le fichier `__builtins__.py` ne fonctionnera pas.

L'extension Python n'importe pas automatiquement les fonctions d'autres fichiers comme le fait le jeu. Donc, pour éviter d'obtenir des avertissements "non défini" dans l'éditeur lorsque vous appelez des fonctions d'autres fichiers, vous devrez ajouter la ligne

`from filename import *`

en haut de chaque fichier qui appelle les fonctions de ce fichier (remplacez `filename` par le nom du fichier).
Le jeu ignorera ces instructions.

Dans le jeu, assurez-vous d'avoir l'option "File Watcher" activée. Maintenant, chaque fois que vous enregistrez dans VS Code, les changements apparaîtront automatiquement dans le jeu.

C'est tout ! Maintenant, vous pouvez écrire votre code dans un éditeur de code professionnel !
