# Tournesols

Les [tournesols](objects/sunflower) collectent la puissance du soleil. Tu peux récolter cette puissance.

La plantation fonctionne exactement comme pour les carottes ou les citrouilles.

Récolter un tournesol mature produit de l'énergie.
S'il y a au moins 10 tournesols dans la ferme et que tu récoltes celui qui a le plus grand nombre de pétales, tu obtiens 5 fois plus d'énergie !

`measure()` renvoie le nombre de pétales du tournesol sous le drone.
Les tournesols ont au minimum `7` et au maximum `15` pétales.
Ils peuvent être mesurés avant même d'être complètement développés.

Plusieurs tournesols peuvent avoir le même nombre de pétales, il peut donc y avoir plusieurs tournesols avec le plus grand nombre de pétales. Dans ce cas, peu importe lequel tu récoltes.

Tant que tu as de l'énergie, le drone fonctionnera deux fois plus vite.
Il consomme 1 point d'énergie toutes les 30 actions (comme les déplacements, les récoltes, les plantations...)
L'exécution d'autres instructions de code peut aussi utiliser de l'énergie, mais beaucoup moins que les actions du drone.

En général, tout ce qui est accéléré par les améliorations de vitesse est également accéléré par l'énergie.
Tout ce qui est accéléré par l'énergie utilise aussi de l'énergie proportionnellement au temps d'exécution, indépendamment des améliorations de vitesse.

