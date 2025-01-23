# Classement
Si vous êtes arrivé jusqu'ici, vous avez surmonté de nombreux défis. Mais les avez-vous résolus efficacement ?
Vous pouvez vous mesurer aux autres joueurs sur différents classements pour trouver les méthodes de farming les plus efficaces.

Vous pouvez démarrer une partie classée en appelant `leaderboard_run(leaderboard, filename, speedup)`.
Cela lance une [simulation](docs/unlocks/simulation.md) similaire à `simulate()` mais avec des conditions de départ fixes. Chaque catégorie de classement a des conditions de départ et de réussite différentes.

La partie classée réussit si la condition de réussite est `True` quand la simulation se termine.
Si la partie est réussie, votre temps sera ajouté au classement.

Pour réduire la variance, toutes les parties doivent durer au moins 2 heures (Vous pouvez accélérer la simulation, donc cela ne prendra pas autant de temps). Si une partie se termine plus tôt, elle sera répétée jusqu'à atteindre un temps total de 2 heures. La moyenne de toutes les parties sera ensuite téléchargée comme votre score.

## Reset le Plus Rapide
Le reset le plus rapide est la catégorie la plus prestigieuse. Automatisez complètement le jeu d'une seule parcelle de ferme jusqu'au déblocage des classements.

Vous n'avez pas besoin de tout débloquer, essayez juste de débloquer `Unlocks.Leaderboard` le plus rapidement possible.

N'oubliez pas que vous pouvez utiliser `num_unlocked(unlock) > 0` pour vérifier si quelque chose est débloqué et vous pouvez utiliser `get_cost()` sur les débloquables pour voir ce qu'ils coûtent afin de pouvoir automatiquement farmer les bons objets.

Appel de Fonction :
`leaderboard_run(Leaderboards.Fastest_Reset, filename, speedup)`

Simulation Équivalente :
`unlocks = {}
items = {}
globals = {}
#une valeur de seed négative signifie une seed aléatoire
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Condition de Réussite :
`num_unlocked(Unlocks.Leaderboard) > 0`

## Labyrinthe
Commencez avec tout débloqué et farmez `300000` d'or le plus rapidement possible. C'est exactement la quantité d'or que vous gagnerez en résolvant un labyrinthe `300` fois.

Appel de Fonction :
`leaderboard_run(Leaderboards.Maze, filename, speedup)`

Simulation Équivalente :
`unlocks = Unlocks
items = {Items.Weird_Substance : 1000000, Items.Power: 1000000}
globals = {}
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Condition de Réussite :
`num_items(Items.Gold) >= 300000`

## Dinosaure
Commencez avec tout débloqué et farmez `98010` os le plus rapidement possible. C'est exactement le nombre d'os que vous obtiendrez en remplissant une zone de 10x10 avec votre queue.

Appel de Fonction :
`leaderboard_run(Leaderboards.Dinosaur, filename, speedup)`

Simulation Équivalente :
`unlocks = Unlocks
items = {Items.Pumpkin : 1000000, Items.Power: 1000000}
globals = {}
seed = -1
simulate(filename, unlocks, items, globals, seed, speedup)`

Condition de Réussite :
`num_items(Items.Bone) >= 98010`

## Autres Classements de Ressources
Chaque plante a son propre classement pour farmer cette ressource particulière le plus rapidement possible. Vous commencez avec tous les débloquables, les ressources nécessaires pour faire pousser la plante, et beaucoup d'énergie. L'objectif est de farmer `100000` de la ressource produite par la plante.

Appels de Fonction :
`leaderboard_run(Leaderboards.Cactus, filename, speedup)`
`leaderboard_run(Leaderboards.Sunflowers, filename, speedup)`
`leaderboard_run(Leaderboards.Pumpkins, filename, speedup)`
`leaderboard_run(Leaderboards.Wood, filename, speedup)`
`leaderboard_run(Leaderboards.Carrots, filename, speedup)`
`leaderboard_run(Leaderboards.Hay, filename, speedup)`
`leaderboard_run(Leaderboards.Polyculture, filename, speedup)`

Condition de Réussite :
`num_items(resource) >= 100000`

`Leaderboards.Polyculture` nécessite de farmer `100000` de chacune des trois ressources de polyculture.
