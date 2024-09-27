# Amélioration de la Vitesse
La vitesse d'exécution a été doublée. Le problème est que le drone récolte maintenant plus vite que l'herbe ne peut pousser, ce qui entraîne une absence totale de récolte. Pour résoudre ce problème, les branches [if](docs/scripting/if) et la fonction [can_harvest](functions/can_harvest) sont maintenant débloquées.

## Vérification Avant la Récolte
Jusqu'à présent, nous n'avions que `True` et `False` comme conditions, ce qui n'est bien sûr pas très utile avec `if`.

La nouvelle fonction `can_harvest()` offre une meilleure condition. `can_harvest()` retourne `True` si la plante sous le drone peut être récoltée et `False` sinon.

`if can_harvest():
	#do something`

La raison pour laquelle vous pouvez utiliser cette fonction comme condition de cette manière est qu'elle retourne une valeur booléenne.

Une valeur de retour signifie essentiellement qu'après l'exécution de la fonctionnalité, l'expression d'appel de fonction s'évalue à la valeur retournée.

Ce qui se passe lorsque le code ci-dessus s'exécute :
- l'if s'exécute
- `can_harvest()` est appelé
- `can_harvest()` fait son travail
- `can_harvest()` retourne `True` ou `False`
- l'instruction est maintenant `if True:` ou `if False:`
- le drone fait une pirouette s'il peut récolter

Nous pouvons maintenant utiliser `if` pour empêcher le drone de récolter trop tôt.