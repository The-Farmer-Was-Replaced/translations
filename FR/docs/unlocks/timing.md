# Chronométrage
Si vous voulez vraiment optimiser vos méthodes, vous devez comprendre comment le temps est mesuré dans ce jeu. Ce déblocage explique tout cela.

## Nouvelles Fonctions
Il existe deux fonctions utiles pour mesurer la durée des choses :

`get_time()` renvoie le temps en secondes depuis le début du jeu.

`get_tick_count()` renvoie le nombre de ticks effectués depuis le début de l'exécution.

Ces deux fonctions ainsi que `quick_print()` sont totalement gratuites. Même l'opération d'appel est gratuite pour elles.

## Détails d'Exécution

### Avertissement
Ce n'est pas ainsi que fonctionne la performance dans le monde réel. Ce sont juste des règles inventées pour ce jeu.
Vous ne vous en soucierez probablement que si vous voulez hyper-optimiser votre code.

L'unité de base du temps pour l'exécution du code s'appelle un "tick". Sans améliorations de vitesse et d'énergie, l'exécution se déroule à un rythme de `400` ticks par seconde.

En général, les opérations qui combinent deux valeurs comme `+, -, *, /, //, %, and, or, ...` prennent un tick pour s'exécuter.
Le `-` à valeur unique et `not` sont gratuits.
Une branche `if` prend également un tick pour s'exécuter (en plus du temps nécessaire pour évaluer l'expression de condition).
Les appels de fonctions et les lectures/écritures de variables sont gratuits, mais les définitions de fonctions prennent 1 tick.
Les instructions `import` sont gratuites.
L'accès à un module importé avec l'opérateur `.` est gratuit.
Si une fonction ou un module a été transmis via des arguments ou des affectations de variables, son utilisation coûtera 1 tick au lieu de 0.
Les boucles `for` et `while` prennent un tick pour démarrer, mais les itérations sont gratuites (sans compter le temps d'évaluation des expressions de condition/séquence).
`return`, `break` et `continue` sont tous gratuits.
`pass` prend un tick et peut donc être utilisé pour créer des délais précis.
L'indexation dans une structure de données prend un tick pour l'opérateur d'index et, dans le cas d'un dictionnaire ou d'un ensemble, des ticks supplémentaires selon la taille de la clé.

Le nombre de ticks que les fonctions intégrées prennent pour s'exécuter est documenté dans la documentation de chaque fonction individuellement.
