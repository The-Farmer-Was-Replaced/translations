# Arrosage

Les plantes poussent plus rapidement lorsqu'elles sont arrosées. Le sol a un niveau d'eau allant de `0` à `1`.

La fonction `get_water()` renvoie le niveau d'eau du sol sur lequel elle est appliquée.

La vitesse de croissance d'une plante poussant sur un sol labouré augmente linéairement de 1x à un niveau d'eau de 0 à 5x à un niveau d'eau de 1. L'arrosage n'affecte que les plantes poussant sur un sol labouré. Il n'a aucun effet sur les plantes poussant sur du gazon.

Le sol s'assèche avec le temps : l'eau perd 1 % de son niveau actuel de temps en temps. Maintenir un niveau d'eau élevé consomme beaucoup plus d'eau que de le maintenir bas.

Vous pouvez utiliser des réservoirs d'eau pour arroser vos plantes. Vous pouvez acheter des réservoirs vides en bois en utilisant `trade(Items.Empty_Tank)`.

Un réservoir peut contenir `0.25` d'eau.

Les réservoirs se remplissent automatiquement. Le taux de remplissage est de `0.5` % du nombre de réservoirs vides par seconde. Donc, si vous avez `100` réservoirs vides, l'un d'eux se remplira toutes les `2` secondes.

Appelez `use_item(Items.Water_Tank)` sur n'importe quel sol pour vider un réservoir et arroser le sol.