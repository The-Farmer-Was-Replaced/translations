# Déboguer

Parfois, votre code ne fonctionne tout simplement pas et vous devez découvrir pourquoi. Il existe quelques outils pour vous aider à le faire.

Le premier est d'exécuter le programme étape par étape. 
Vous pouvez passer en mode pas à pas avec le bouton à côté du bouton Exécuter ou en définissant un point d'arrêt.

Les points d'arrêt peuvent être ajoutés en cliquant sur le panneau de point d'arrêt à gauche du code.
![](Breakpoints227)
Lorsque l'exécution atteint la ligne où se trouve le point d'arrêt, elle passera automatiquement en mode pas à pas.

Lorsque vous survolez une variable, sa valeur actuelle s'affiche.

La fonction `print()` peut également être très utile. Elle imprimera toute valeur qui lui est passée directement dans l'air.

Exemples :

`print(0.24) #imprime "0.24"

print(can_harvest()) #imprime "True" ou "False"

print(get_pos_x(), get_pos_y()) #imprime la position actuelle`

La fonction print imprime la valeur directement dans l'air et sur la page [Output](docs/output.md).

Imprimer dans l'air peut parfois être un peu lent si vous souhaitez imprimer beaucoup de valeurs. 
Dans ce cas, vous pouvez utiliser la fonction `quick_print()` qui imprime uniquement dans la fenêtre de sortie.

La fenêtre de sortie enregistre également les avertissements et les erreurs, donc si quelque chose ne fonctionne pas comme prévu, il peut être utile de vérifier cela.

Lorsque l'exécution s'arrête, la sortie est également écrite dans le fichier output.txt dans le dossier du jeu. Vous pouvez trouver le dossier du jeu en sélectionnant Menu -> Charger -> Ouvrir le dossier.