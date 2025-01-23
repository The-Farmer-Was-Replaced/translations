
# Importation
Mettre tout votre code dans un seul fichier devient rapidement ingérable.
Les instructions `import` vous permettent d'importer des fonctions et des variables globales d'un autre fichier.

`import nom_fichier`

C'est la forme la plus simple d'une instruction d'importation. Cela vous donne accès à tout ce qui est défini dans le fichier nommé `nom_fichier`. Chaque fenêtre dans le jeu est un fichier, et le nom du fichier est le nom affiché en haut de la fenêtre.

Voici un exemple avec deux fichiers :
Fichier nommé helper :
`x = 0

def say_hello():
    print("bonjour de helper")`

Autre fichier :
`import helper
helper.say_hello()
helper.x += 1`

Ici, `import helper` exécute le fichier nommé `helper` et vous donne accès à tous ses globaux.
Vous pouvez ensuite accéder aux variables et fonctions dans le module importé en utilisant l'opérateur `.`.
Donc dans cet exemple, `helper.say_hello()` appelle `say_hello()` à l'intérieur de helper et la dernière ligne incrémente la variable globale x.

Vous pouvez également déplacer les globaux du module importé dans la portée actuelle où l'instruction d'importation est exécutée en utilisant la syntaxe `from`.

`from helper import *`
Importe tous les globaux de helper.

ou

`from helper import say_hello`
Importe uniquement les globaux spécifiés de helper.

Cela importe également le fichier helper, mais au lieu d'y accéder via une variable nommée `helper`, il décompresse les globaux de `helper` et les assigne directement dans la portée locale.

`from helper import say_hello
say_hello()`

Cette forme d'importation n'est généralement pas recommandée car elle ne fonctionne pas bien lorsque deux fichiers s'importent mutuellement, et vous pouvez accidentellement écraser des variables dans le fichier importateur en raison de collisions de noms.

# Comment ça marche vraiment

## Résumé
Les importations peuvent être assez contre-intuitives, mais la plupart des problèmes peuvent être évités en s'en tenant à la syntaxe `import fichier` au lieu de `from fichier import`, et en enveloppant tout ce qui n'est pas une définition globale dans
`if __name__ == "__main__":`

## Effets Secondaires des Importations
La première fois que vous importez un fichier, il exécutera tout le fichier, puis vous donnera accès à toutes les variables qui ont été définies pendant l'exécution.
Si vous importez à nouveau le même fichier, il retournera simplement le module mis en cache de la première fois.

Cela signifie que les instructions d'importation peuvent avoir des effets secondaires. Si vous importez un fichier qui appelle `harvest()`, il récoltera effectivement lors de l'importation. Mais lorsque vous l'importez à nouveau, il ne récoltera pas à nouveau parce que le fichier n'est exécuté qu'une seule fois.

Il existe un moyen d'éviter ces effets secondaires en utilisant la variable `__name__`. C'est une variable qui est automatiquement définie sur `"__main__"` lorsqu'un fichier est exécuté directement, et sur le nom du fichier lorsqu'un fichier est exécuté via `import`.
Il est considéré comme une bonne pratique de mettre tout code que vous ne voulez pas exécuter lorsque le fichier est importé à l'intérieur d'un bloc `if __name__ == "__main__":`.

Une structure de fichiers courante en Python est de mettre le code qui doit être exécuté lorsque le fichier est lancé dans une fonction `main()`. De cette façon, vous avez une distinction claire entre les variables locales (définies à l'intérieur de `main()`) et les variables globales qui peuvent être importées (définies en dehors de `main()`).

`a_global_variable = "global"

def main():
    a_local_variable = "local"
    // faire des choses

if __name__ == "__main__":
    main()`

## Cycles d'Importation
Que se passe-t-il si le fichier `a` importe le fichier `b` et le fichier `b` importe le fichier `a` ?

fichier `a` :
`import b
x = 0`

fichier `b` :
`import a
def f():
    print(a.x)`

Cela fonctionnera correctement. Supposons qu'aucun des deux fichiers n'est encore chargé, et que quelqu'un exécute `import a`.

- `a` s'exécute jusqu'à la ligne `import b`.
- `b` s'exécute jusqu'à la ligne `import a`.
- Le module `a` existe déjà, mais ne contient pas `x` car il n'a exécuté que jusque la ligne `import b`.
- `b` stocke une référence au module `a` partiellement chargé dans une variable appelée `a`.
- `b` exécute la déclaration `def` et stocke la fonction `f()`.

Lorsque quelqu'un appelle `b.f()`, il imprimera correctement `0` car le module `a` auquel `b` a une référence est maintenant complètement chargé.

Maintenant, considérez le même code en utilisant la syntaxe `from`.

fichier `a` :
`from b import *
x = 0`

fichier `b` :
`from a import *
def f():
    print(x)`

- `a` s'exécute jusqu'à la ligne `from b import *`.
- `b` s'exécute jusqu'à la ligne `from a import *`.
- Le module `a` existe déjà, mais n'a pas encore été complètement exécuté.
- `b` décompresse tout ce qui est actuellement dans `a` dans son propre espace de noms global. À ce stade, `a` ne contient rien car il n'a pas encore atteint la ligne `x = 0`, donc rien n'est importé.
- `b` exécute la déclaration `def` et stocke la fonction `f()`.

Si quelqu'un appelle maintenant `b.f()`, il obtiendra une erreur indiquant que `x` n'existe pas dans l'espace de noms actuel. Cela est dû au fait que cette fois, `b` n'a pas de référence au `a` encore en cours de chargement et ne voit pas les définitions qui ont été ajoutées après l'importation.
Les importations peuvent être assez contre-intuitives, mais la plupart des problèmes peuvent être évités en s'en tenant à la syntaxe `import fichier` au lieu de `from fichier import`, et en enveloppant tout ce qui n'est pas une définition globale dans


`a_global_variable = "global"

def main():

Cela fonctionnera correctement. Supposons qu'aucun des deux fichiers n'est encore chargé, et que quelqu'un exécute `import a`.

- `a` s'exécute jusqu'à la ligne `import b`.
- `b` s'exécute jusqu'à la ligne `import a`.
- Le module `a` existe déjà, mais ne contient pas `x` car il n'a exécuté que jusqu'à la ligne `import b`.
- `b` stocke une référence au module `a` partiellement chargé dans une variable appelée `a`.
- `b` exécute la déclaration `def` et stocke la fonction `f()`.

Lorsque quelqu'un appelle `b.f()`, il imprimera correctement `0` car le module `a` auquel `b` a une référence est maintenant complètement chargé.


Si quelqu'un appelle maintenant `b.f()`, il obtiendra une erreur indiquant que `x` n'existe pas dans l'espace de noms actuel. Cela est dû au fait que cette fois, `b` n'a pas de référence au `a` encore en cours de chargement et ne voit pas les définitions qui ont été ajoutées après l'importation.
fichier `b` :
`from a import *
- `b` exécute la déclaration `def` et stocke la fonction `f()`.
def f():
- `b` décompresse tout ce qui est actuellement dans `a` dans son propre espace de noms global. À ce stade, `a` ne contient rien car il n'a pas encore atteint la ligne `x = 0`, donc rien n'est importé.
    print(x)`

- `a` s'exécute jusqu'à la ligne `from b import *`.
- `b` s'exécute jusqu'à la ligne `from a import *`.
- Le module `a` existe déjà, mais n'a pas encore été complètement exécuté.

Maintenant, considérez le même code en utilisant la syntaxe `from`.

fichier `a` :
`from b import *
x = 0`
    a_local_variable = "local"
    // faire des choses

x = 0`

fichier `b` :
`import a
def f():
    print(a.x)`
if __name__ == "__main__":
    main()`
Que se passe-t-il si le fichier `a` importe le fichier `b` et le fichier `b` importe le fichier `a` ?

fichier `a` :
`import b

## Cycles d'Importation
Une structure de fichiers courante en Python est de mettre le code qui doit être exécuté lorsque le fichier est lancé dans une fonction `main()`. De cette façon, vous avez une distinction claire entre les variables locales (définies à l'intérieur de `main()`) et les variables globales qui peuvent être importées (définies en dehors de `main()`).
`if __name__ == "__main__":`


Il est considéré comme une bonne pratique de mettre tout code que vous ne voulez pas exécuter lorsque le fichier est importé à l'intérieur d'un bloc `if __name__ == "__main__":`.
Il existe un moyen d'éviter ces effets secondaires en utilisant la variable `__name__`. C'est une variable qui est automatiquement définie sur `"__main__"` lorsqu'un fichier est exécuté directement, et sur le nom du fichier lorsqu'un fichier est exécuté via `import`.
## Effets Secondaires des Importations
La première fois que vous importez un fichier, il exécutera tout le fichier, puis vous donnera accès à toutes les variables qui ont été définies pendant l'exécution.

Cela signifie que les instructions d'importation peuvent avoir des effets secondaires. Si vous importez un fichier qui appelle `harvest()`, il récoltera effectivement lors de l'importation. Mais lorsque vous l'importez à nouveau, il ne récoltera pas à nouveau parce que le fichier n'est exécuté qu'une seule fois.
Si vous importez à nouveau le même fichier, il retournera simplement le module mis en cache de la première fois.

Cette forme d'importation n'est généralement pas recommandée car elle ne fonctionne pas bien lorsque deux fichiers s'importent mutuellement, et vous pouvez accidentellement écraser des variables dans le fichier importateur en raison de collisions de noms.

# Comment ça marche vraiment

## TLDR

`from helper import say_hello
say_hello()`

Cela importe également le fichier helper, mais au lieu d'y accéder via une variable nommée `helper`, il décompresse les globaux de `helper` et les assigne directement dans la portée locale.
Importe uniquement les globaux spécifiés de helper.
Importe tous les globaux de helper.

ou

`from helper import say_hello`

Vous pouvez également déplacer les globaux du module importé dans la portée actuelle où l'instruction d'importation est exécutée en utilisant la syntaxe `from`.

`from helper import *`
Donc dans cet exemple, `helper.say_hello()` appelle `say_hello()` à l'intérieur de helper et la dernière ligne incrémente la variable globale x.
Vous pouvez ensuite accéder aux variables et fonctions dans le module importé en utilisant l'opérateur `.`.

Ici, `import helper` exécute le fichier nommé `helper` et vous donne accès à tous ses globaux.

C'est la forme la plus simple d'une instruction d'importation. Cela vous donne accès à tout ce qui est défini dans le fichier nommé `nom_fichier`. Chaque fenêtre dans le jeu est un fichier, et le nom du fichier est le nom affiché en haut de la fenêtre.

Voici un exemple avec deux fichiers :
Fichier nommé helper :
`x = 0
helper.say_hello()
helper.x += 1`

def say_hello():
    print("bonjour de helper")`

Autre fichier :
`import helper
# Importation
Mettre tout votre code dans un seul fichier devient rapidement ingérable.
Les instructions `import` vous permettent d'importer des fonctions et des variables globales d'un autre fichier.

`import nom_fichier`
