# Simulation

Les simulations vous permettent de tester rapidement du code sans modifier l'état de la ferme réelle.
L'état initial de la simulation peut être choisi librement, et lorsque la simulation se termine, la ferme réelle sera exactement dans l'état où elle était avant le début de la simulation.

La fonction `simulate()` est utilisée pour démarrer une simulation.

Le fichier dans lequel l'exécution doit commencer
`filename = "f1"`

Commencer avec tout débloqué et entièrement amélioré
`sim_unlocks = Unlocks`

Commencer avec 10000 carottes et 50 foin
`sim_items = {Items.Carrot : 10000, Items.Hay : 50}`

Commencer avec une variable globale "a" avec une valeur de 13
`sim_globals = {"a" : 13}`

Utiliser une graine aléatoire fixe
`seed = 0`

Accélérer la simulation d'un facteur 64
`speedup = 64`

Exécuter la simulation
`run_time = simulate(filename, sim_unlocks, sim_items, sim_globals, seed, speedup)`

La fonction `simulate()` renvoie le temps, en secondes, qu'il a fallu pour simuler le fichier de départ donné.

### Nom du Fichier
Le premier argument de la fonction simulate est le nom du fichier. C'est le nom qui s'affiche en haut de la fenêtre de code. La simulation exécutera le fichier spécifié comme si vous aviez cliqué sur le bouton Exécuter.

### Débloquages Initiaux
Toutes les fonctionnalités de programmation comme les boucles, les instructions if, les listes, les dictionnaires,... resteront toujours débloquées.

Le deuxième argument vous permet de spécifier avec quels débloquages/améliorations la simulation doit démarrer en plus des fonctionnalités de programmation. Cela doit être une séquence de débloquages. La simulation démarrera avec tous les débloquages de la séquence améliorés à leur niveau maximum.

Si vous souhaitez spécifier un niveau d'amélioration autre que le maximum, vous pouvez passer un dictionnaire qui associe les débloquages aux niveaux de débloquage. Dans ce cas, les valeurs négatives correspondent au niveau de débloquage maximum.

### Objets Initiaux
Le troisième argument vous permet de passer un dictionnaire qui associe des objets à des nombres. Il spécifie les objets avec lesquels démarrer la simulation.

### Variables Globales Initiales
Comme la simulation démarre une exécution de programme complètement nouvelle, vous ne pouvez pas accéder aux variables du programme qui démarre la simulation.
Cependant, il est possible de passer des valeurs à la simulation en utilisant le quatrième argument. C'est un dictionnaire qui associe des noms de variables sous forme de chaînes à des valeurs. Ces variables sont ensuite ajoutées à la portée globale de l'exécution à l'intérieur de la simulation.

Notez que cela copie toutes les valeurs, donc les modifier à l'intérieur de la simulation n'affectera pas les valeurs originales en dehors de la simulation. Il n'est pas possible de renvoyer des valeurs de la simulation autres que le temps qu'il a fallu pour l'ex
