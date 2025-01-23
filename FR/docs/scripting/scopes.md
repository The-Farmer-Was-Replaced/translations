# Portées de Noms

Les portées déterminent quelles variables peuvent être accessibles d'où. Une portée est essentiellement une correspondance de noms à des valeurs. Elles fonctionnent essentiellement de la même manière qu'en Python.

Il y a une portée globale et chaque fonction a une portée locale. Lorsque vous définissez une variable, elle est ajoutée à la portée actuelle. Tout ce qui est en dehors d'une définition de fonction est considéré comme faisant partie de la portée globale.

`x = 1`
Assigne une valeur de `1` au nom `x` dans la portée globale.

Cette instruction `def` assigne une fonction au nom `f` dans la portée globale.

```python
def f():
    `Assigne une valeur de `1` au nom `y` dans la portée locale de `f`.`
    y = 1

    `Assigne une fonction au nom `g` dans la portée locale de `f`.`
    def g():
        pass
```

`f()`
Récupère la fonction stockée dans `f` de la portée globale et l'appelle.

`print(y)`
Cette instruction print dans la portée globale génère une erreur car `y` n'a jamais été déclarée dans la portée globale, donc nous ne pouvons pas la lire ici. Elle n'existait que dans la portée locale de `f`.

## Le mot-clé global

Par défaut, toutes les variables dans les fonctions sont liées à la portée locale, même si une variable du même nom existe dans la portée globale.

```python
x = 0

def f():
    x = 1
f()
print(x)
```

Ce code affiche `0` parce que le `x` local à l'intérieur de `f` n'est pas la même variable que le `x` global, donc le `x` global reste inchangé. Ceci est important car sinon un appel de fonction pourrait écraser accidentellement une variable globale qui a simplement le même nom qu'une variable locale de cette fonction.

Si vous voulez écrire sur une variable globale, vous devez le faire explicitement en utilisant le mot-clé `global`.

```python
x = 0

def f():
    global x
    x = 1
f()
print(x)
```

Dans cet exemple, `global x` lie `x` à la variable globale `x` définie au-dessus. Cela affichera maintenant `1`. Notez que changer des variables globales est généralement le premier pas vers un code spaghetti, où chaque partie du programme affecte toutes les autres parties du programme, donc ne l'abusez pas.

## Boucles et branches

Les boucles et branches ne créent pas leurs propres portées, donc tout ce qui est déclaré à l'intérieur peut toujours être utilisé à l'extérieur.

```python
for i in range(3):
    pass
print(i)
```

Cela imprimera `2` parce que la dernière itération de la boucle `for` a assigné `2` à `i`.
