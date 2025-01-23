
# Notes de Mise à Jour

### Changements Majeurs :
Vous devrez les modifier dans votre code.

Les fonctions définies dans d'autres fichiers (fenêtres dans le jeu) ne sont plus importées implicitement. Vous devez maintenant débloquer et utiliser des instructions d'importation explicites comme en Python (voir déblocage d'importation).

### Changements Majeurs des Patches Anciens que Vous Auriez Pu Manquer :
- `Items.Bones` a été renommé en `Items.Bone` afin que tous les items soient au singulier.
- `Entities.Carrots` a été renommé en `Entities.Carrot` afin que toutes les entités soient au singulier.
- `Grounds.Turf` a été renommé en `Grounds.Grassland` pour faciliter la compréhension.
- `Items.Water_Tank` a été renommé en `Items.Water` car la fonctionnalité de remplissage du réservoir a été supprimée.
- `Unlocks.Benchmark` a été remplacé par `Unlocks.Timing`.
- `get_op_count()` a été renommé en `get_tick_count()`.
- `set_farm_size()` a été renommé en `set_world_size()` pour être cohérent avec `get_world_size()`.
- `get_companion()` renvoie maintenant un tuple de la forme (entity, (x, y)) au lieu d'une liste.
- `trade()` a été supprimé du jeu.

### Variables Globales :
- Les scopes et les variables globales ont été modifiés pour fonctionner comme en Python. Cela signifie que vous pouvez maintenant utiliser le mot-clé `global` pour écrire dans le scope global.
- Il y a maintenant une erreur lors de l'utilisation d'une variable locale avant son assignation locale, même s'il existe une variable globale avec le même nom.
- Les messages d'erreur de masquage ont été supprimés.

### Importations :
L'ancien système d'importation importait automatiquement toutes les fonctions de tous les fichiers. Cela avait le gros inconvénient que les variables globales des autres fichiers ne pouvaient pas être importées et étaient donc inaccessibles.
Le nouveau système d'importation est une version légèrement simplifiée de la façon dont les importations fonctionnent en Python. Vous pouvez importer un module en utilisant la syntaxe `import file` ou `from file import *`.

### Autres Changements :
- Ajout de la fonction `str()`.
- Ajout du support de la déstructuration dans les boucles for.
- Divers changements dans la documentation.
- Correction du passage des fonctions dans les simulations.
- Correction de l'utilisation de `in` et `not in` avec les fonctions.
- Correction de la fonction set permettant des listes comme clés.
