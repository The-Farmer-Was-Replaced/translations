# Débogage

Parfois, votre code ne fonctionne tout simplement pas et vous devez comprendre pourquoi. Il existe quelques outils pour vous aider.

La première consiste à exécuter le programme étape par étape.
Vous pouvez passer en mode étape par étape avec le bouton à côté du bouton Exécuter ou en définissant un point d'arrêt.

Les points d'arrêt peuvent être ajoutés en cliquant sur le panneau des points d'arrêt à gauche du code.
![](Breakpoints227)
Lorsque l'exécution atteint la ligne où se trouve le point d'arrêt, elle passe automatiquement en mode étape par étape.

Lorsque vous survolez une variable, sa valeur actuelle est affichée.

La fonction `print()` peut également être très utile. Elle imprimera toute valeur passée directement dans l'air.

Exemples :

`print(0.24) #imprime "0.24"

print(can_harvest()) #imprime "True" ou "False"

print(get_pos_x(), get_pos_y()) #imprime la position actuelle`

La fonction print affiche la valeur directement dans l'air et sur la page [Sortie](docs/output.md).

Imprimer dans l'air peut parfois être un peu lent si vous souhaitez imprimer beaucoup de valeurs.
Dans ce cas, vous pouvez utiliser la fonction `quick_print()` qui imprime uniquement dans la fenêtre de sortie.

La fenêtre de sortie enregistre également les avertissements et les erreurs, il peut donc être utile de vérifier cela si quelque chose ne fonctionne pas comme prévu.

Lorsque l'exécution s'arrête, la sortie est également écrite dans le fichier output.txt dans le dossier du jeu. Vous pouvez trouver le dossier du jeu en sélectionnant Menu -> Charger -> Ouvrir le Dossier.
