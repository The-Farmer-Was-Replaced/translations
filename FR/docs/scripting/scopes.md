# Noms des Portées

Les portées déterminent quelles variables peuvent être accédées depuis où. Une portée est essentiellement une correspondance entre des noms et des valeurs. Elles fonctionnent presque de la même manière qu'en Python, mais pas toujours, alors assurez-vous de lire cette section attentivement.

Tout comme Python, il existe une portée globale, et chaque fonction a une portée locale. Lorsque vous définissez une variable, elle est ajoutée à la portée actuelle. Tout ce qui est en dehors d'une définition de fonction est considéré comme faisant partie de la portée globale.

`x = 1`
Attribue une valeur de `1` au nom `x` dans la portée globale.

Cette instruction `def` attribue une fonction au nom `f` dans la portée globale.

```python
def f():
    `Attribue une valeur de `1` au nom `y` dans la portée locale de `f`.`
    y = 1

    `Attribue une fonction au nom `g` dans la portée locale de `f`.`
    def g():
        pass
```

`f()`
Récupère la fonction stockée dans `f` depuis la portée globale et l'appelle.

`print(y)`
Cette instruction print dans la portée globale génère une erreur car `y` n'a jamais été déclaré dans la portée globale, donc nous ne pouvons pas le lire ici. Il n'existait que dans la portée locale de `f`.

Les boucles et les branches ne créent pas leurs propres portées, donc tout ce qui est déclaré à l'intérieur peut encore être utilisé à l'extérieur.

```python
for i in range(3):
    pass
print(i)
```

Cela imprimera `2` car la dernière itération de la boucle `for` a attribué `2` à `i`.

Tout jusqu'ici est le même en Python. La première différence réside dans la façon dont les définitions globales d'autres fichiers sont importées. Python utilise l'instruction import pour cela, le jeu importe automatiquement les fonctions globales.

Toutes les fonctions définies dans les fichiers chargés seront ajoutées à la portée globale avant l'exécution, vous pouvez donc utiliser des fonctions déclarées dans d'autres fichiers. Notez que ce n'est pas le cas pour les variables globales. Elles ne sont disponibles que lorsque la ligne où elles sont attribuées est effectivement exécutée. Seule la portée globale de la fenêtre sur laquelle vous cliquez sur le bouton d'exécution sera exécutée.

Les variables de la portée globale peuvent être lues n'importe où, mais les attributions seront toujours affectées à la portée locale.

```python
x = 1

def f():
    x += 1

f()

print(x)
```

Ce code imprime `1` et non `2` car `x += 1` lira d'abord `1` de la variable globale `x` puis attribuera `2` à une nouvelle variable locale également appelée `x`. Ainsi, la variable globale `x` n'est jamais modifiée.

Ce comportement diffère légèrement de celui de Python. Python génère une erreur ici car vous essayez de lire à partir d'une variable locale avant qu'elle ne soit attribuée.

En Python, il est également possible d'utiliser le mot-clé 'global' pour déclarer que vous souhaitez utiliser la variable globale au lieu de la locale, mais cela n'est pas pris en charge dans ce jeu.

Si vous avez vraiment besoin de mettre à jour des variables globales, vous pouvez utiliser un dictionnaire pour cela. Ils utilisent la sémantique de référence, ce qui signifie que la variable contient une référence au dictionnaire sous-jacent, plutôt que de stocker directement la structure de données dans la variable. Une variable globale peut stocker une référence à un dictionnaire qui peut être lu dans une fonction. Vous pouvez modifier le dictionnaire sous-jacent sans mettre à jour la variable dans la portée globale. Comme la variable dans la portée globale pointe toujours vers le même dictionnaire, elle reflétera également toutes les modifications apportées à ce dictionnaire. Pour illustrer, considérez le code suivant :

Attribuer un dictionnaire dans la portée globale

```python
d = {"x": 1}

def f():
    `effectuer un changement au dictionnaire référencé par `d`.`
    d["x"] += 1

`imprime `2`
print(d["x"])
```