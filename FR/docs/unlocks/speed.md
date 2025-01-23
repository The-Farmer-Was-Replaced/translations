# Amélioration de Vitesse
La vitesse d'exécution a été doublée. Le problème est que le drone récolte maintenant plus vite que l'herbe ne peut pousser, ce qui ne donne aucune récolte. Pour gérer cela, les instructions [if](docs/scripting/if.md) et la fonction [can_harvest](functions/can_harvest) sont maintenant débloquées.

## Vérifier Avant de Récolter
Jusqu'à présent, nous n'avions que `True` et `False` comme conditions, ce qui n'est évidemment pas très utile avec `if`.

La nouvelle fonction can_harvest() fournit une meilleure condition. `can_harvest()` renvoie `True` si la plante sous le drone peut être récoltée et `False` sinon.

`if can_harvest():
    #faire quelque chose`

La raison pour laquelle tu peux utiliser cette fonction comme condition est qu'elle renvoie une valeur booléenne.

Une valeur de retour signifie essentiellement qu'après l'exécution de la fonctionnalité, l'expression d'appel de fonction est évaluée à la valeur renvoyée.

Ce qui se passe lorsque le code ci-dessus s'exécute :
    -le if s'exécute
    -`can_harvest()` est appelé
    -`can_harvest()` fait son travail
    -`can_harvest()` renvoie `True` ou `False`
    -l'instruction devient `if True:` ou `if False:`
    -le bloc de code ne s'exécute que s'il peut récolter

Maintenant, nous pouvons utiliser `if` pour empêcher le drone de récolter trop tôt.
