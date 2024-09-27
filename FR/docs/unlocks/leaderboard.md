# Classement

Le défi ultime de l'agriculture automatisée est de jouer au jeu automatiquement aussi vite que possible.

Appeler `timed_reset()` sauvegardera le jeu, réinitialisera tous les déblocages et améliorations qui ne concernent pas la programmation, et démarrera le chronomètre du classement.

Vous conservez toutes les fonctionnalités linguistiques comme `while, if, for`, les variables, les opérateurs et les capteurs. Vous conservez également les coûts et les déblocages automatiques afin de pouvoir automatiser complètement le jeu.

Si l'exécution du programme s'arrête, la course est annulée. La course est terminée lorsque l'exécution appelle à nouveau `timed_reset()`. Vous n'avez pas besoin d'avoir tout débloqué, essayez simplement de débloquer `Unlocks.Leaderboard` et d'appeler `timed_reset()` aussi vite que possible.

Après que la course soit terminée ou annulée, la sauvegarde d'avant la course est rechargée.

Pendant que le chronomètre tourne, vous avez la possibilité d'accélérer le temps pour ne pas avoir à attendre trop longtemps.

N'oubliez pas que vous pouvez utiliser `num_unlocked(unlock) > 0` pour vérifier si quelque chose est débloqué et vous pouvez utiliser `get_cost()` sur vos déblocages pour voir ce qu'ils coûtent afin de pouvoir automatiquement cultiver les bons objets.