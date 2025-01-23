
# Import
Mettre tout ton code dans un seul fichier devient rapidement ingérable.
Les instructions `import` te permettent d’importer des fonctions et des variables globales depuis un autre fichier.

`import filename`

C’est la forme la plus simple d’instruction d’importation. Elle te donne accès à tout ce qui est défini dans le fichier nommé `filename`. Chaque fenêtre du jeu est un fichier, et le nom du fichier est celui qui s’affiche en haut de la fenêtre.

Voici un exemple avec deux fichiers :
Fichier nommé helper :
`def say_hello():
    print("hello from helper")`

Un autre fichier :
`import helper
helper.say_hello()`

Ici, `import helper` exécute le fichier helper et te donne accès à toutes ses variables globales.
Tu peux ensuite accéder aux variables et fonctions dans le module importé à l'aide de l’opérateur `.`.
Dans cet exemple, `helper.say_hello()` appelle la fonction `say_hello()` à l’intérieur de helper.

Tu peux aussi déplacer les variables globales du module importé dans le scope actuel où l’instruction d’importation est exécutée en utilisant la syntaxe `from`.

`from helper import *`
Importe toutes les variables globales de helper.

ou

`from helper import say_hello`
N’importe que les variables globales spécifiées de helper.

Cela importe également le fichier helper, mais au lieu d’y accéder via une variable appelée `helper`, cela «décompresse» les variables globales de `helper` et les affecte directement dans le scope local.

`from helper import say_hello
say_hello()`

Cette forme d’importation n’est généralement pas recommandée, car tu peux écraser involontairement des variables dans le fichier d’import en raison de collisions de noms.

## Ce que ça fait vraiment
La première fois que tu importes un fichier, il exécute tout son contenu, puis tu as accès à toutes les variables définies pendant l’exécution.
Si tu importes le même fichier à nouveau, il renverra simplement l’état global mis en cache lors de la première exécution.

Cela signifie que les instructions d’importation peuvent avoir des effets secondaires. Si tu importes un fichier qui appelle `harvest()`, la récolte sera réellement effectuée pendant l’importation. Mais si tu l’importes de nouveau, il ne se réexécutera pas, car le fichier n’est exécuté qu’une seule fois.

Il existe un moyen d’éviter ces effets secondaires en utilisant la variable `__name__`. Cette variable est automatiquement définie sur `"__main__"` lorsqu’un fichier est exécuté directement, et sur le nom du fichier lorsqu’il est exécuté via `import`.
Il est considéré comme une bonne pratique de mettre tout code que tu ne souhaites pas exécuter à l’import dans un bloc `if __name__ == "__main__":`.

Une structure de fichier courante en Python consiste à mettre le code qui doit s’exécuter quand le fichier est lancé directement dans une fonction `main()`. De cette manière, tu as une distinction claire entre les variables locales du script (définies dans `main()`) et les variables globales pouvant être importées (définies en dehors de `main()`).

`a_global = "global value"

def main():
    a_local = "local value"
    //do things

if __name__ == "__main__":
    main()`
