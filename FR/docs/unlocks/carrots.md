# Carottes
Avant de pouvoir planter des carottes avec `plant(Entities.Carrots)`, vous devez faire deux nouvelles choses. Tout d'abord, les carottes ne peuvent pousser que sur un sol labouré. Pour labourer le sol, il suffit d'appeler `till()`. Appeler `till()` à nouveau le changera en `Grounds.Turf`.

La deuxième nouvelle fonctionnalité est que les carottes ont besoin de graines pour pousser. Vous pouvez acheter des graines de carottes avec la nouvelle fonction `trade()`.
Vous devez passer un type d'article à `trade()` comme ceci : `trade(Items.Carrot_Seed)`

Si l'article peut être acheté, alors il sera acheté avec cela.

Vous pouvez voir le coût de n'importe quel article dans son info-bulle. L'info-bulle apparaît lorsque vous survolez l'article lui-même ou le nom de l'article dans le code.