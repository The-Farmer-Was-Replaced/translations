# Tournesols

Les tournesols captent l'énergie du soleil. Vous pouvez récolter cette énergie.

Planter des tournesols fonctionne exactement de la même manière que planter des carottes, sauf que vous devez acheter des graines de tournesol au lieu de graines de carotte.

Cependant, lorsque vous récoltez un tournesol, l'énergie de tous les tournesols de la ferme se concentre dans la plante récoltée. Ainsi, récolter un tournesol produit une énergie égale à la racine carrée du nombre de tournesols sur la ferme.

Seul un des tournesols ayant le plus de pétales peut gérer cela. Si vous récoltez un tournesol qui n'a pas le plus de pétales parmi tous les tournesols de la ferme, l'énergie détruira tous les tournesols de la ferme.

`measure()` retourne le nombre de pétales du tournesol sous le drone. Les tournesols ont au moins `7` et au plus `15` pétales. Ils peuvent être mesurés avant d'être complètement développés.

Plusieurs tournesols peuvent avoir le même nombre de pétales, donc il peut également y avoir plusieurs tournesols avec le plus grand nombre de pétales. Dans ce cas, peu importe lequel vous récoltez.

Tant que vous avez de l'énergie, le drone l'utilisera pour fonctionner deux fois plus vite. Il consomme 1 énergie toutes les 30 actions (comme les déplacements, les récoltes, les plantations...)

Exécuter d'autres instructions de code peut également utiliser de l'énergie, mais beaucoup moins que les actions du drone.

En général, tout ce qui est accéléré par les améliorations de vitesse est également accéléré par l'énergie. Tout ce qui est accéléré par l'énergie utilise également de l'énergie proportionnelle au temps nécessaire pour l'exécuter, en ignorant les améliorations de vitesse.