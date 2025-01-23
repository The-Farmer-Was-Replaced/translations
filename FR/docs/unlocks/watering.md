# Arrosage

Les plantes poussent plus vite lorsqu'elles sont arrosées. Le sol a un niveau d'eau allant de `0` à `1`.

La fonction `get_water()` renvoie le niveau d'eau du sol sur lequel elle se trouve.

La vitesse de croissance d'une plante augmente linéairement de 1x à niveau d'eau 0 jusqu'à 5x à niveau d'eau 1.

Le sol s'assèche avec le temps : Il perd 1% de son eau actuelle environ une fois par seconde. Maintenir un niveau d'eau élevé consommera beaucoup plus d'eau que maintenir un niveau d'eau bas.

Vous pouvez utiliser des réservoirs d'eau pour arroser vos plantes. Un réservoir d'eau est automatiquement ajouté à votre inventaire toutes les 10 secondes.
Améliorer `Unlocks.Watering` vous donnera un réservoir d'eau supplémentaire toutes les 10 secondes.

Un réservoir peut contenir `0.25` d'eau.

Appelez `use_item(Items.Water)` au-dessus de n'importe quel sol pour l'arroser.

